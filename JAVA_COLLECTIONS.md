# Java Collections — минимум для LeetCode

Практический срез Java Collections Framework для решения задач без подсказок IDE (Java 21+). Не вся иерархия
`Iterable`/`Map` целиком — только то, чем реально пользуешься под таймером.

## List (в основном ArrayList)

- `add(x)`, `add(i, x)`, `get(i)`, `set(i, x)`, `size()`, `isEmpty()`, `contains(x)`, `indexOf(x)`.
- ⚠️ **Ловушка**: `remove(int index)` удаляет по индексу, `remove(Integer.valueOf(x))` / `remove((Object) x)` — по
  значению.

```
List<Integer> list = new ArrayList<>(List.of(5, 10, 15));
list.remove(1);               // удалит элемент по индексу 1 -> [5, 15]
list.remove(Integer.valueOf(5)); // удалит элемент со значением 5 -> [15]
```

- `Collections.sort(list)`, `list.sort(Comparator.comparingInt(...))`.

## Deque (ArrayDeque) — стек и очередь в одном

- Как стек: `push(x)`, `pop()`, `peek()`.
- Как очередь: `offer(x)`, `poll()`, `peek()`.
- Как дек (sliding window maximum, monotonic deque): `offerFirst/offerLast`, `pollFirst/pollLast`,
  `peekFirst/peekLast`.
- Не `Stack`/не `LinkedList` напрямую как «канонический» выбор — `ArrayDeque` быстрее и это стандартная практика.

```
Deque<Integer> monoDeque = new ArrayDeque<>();
for (int i = 0; i < nums.length; i++) {
    while (!monoDeque.isEmpty() && nums[monoDeque.peekLast()] < nums[i]) {
        monoDeque.pollLast();          // выкидываем меньшие элементы справа
    }
    monoDeque.offerLast(i);
    if (monoDeque.peekFirst() <= i - k) {
        monoDeque.pollFirst();         // элемент выпал из окна
    }
}
```

## PriorityQueue (heap)

- `new PriorityQueue<>()` — min-heap по умолчанию.
- `new PriorityQueue<>(Comparator.reverseOrder())` — max-heap.
- `offer(x)`, `poll()`, `peek()`.
- Нет `decrease-key` — для Дейкстры решают через дубликаты + флаг «обработан».

```
// топ-K частых элементов: min-heap по частоте размера k
PriorityQueue<int[]> heap = new PriorityQueue<>((a, b) -> a[1] - b[1]); // a[1] = частота
for (var entry : freq.entrySet()) {
    heap.offer(new int[]{entry.getKey(), entry.getValue()});
    if (heap.size() > k) heap.poll();
}

// Дейкстра: очередь по расстоянию, [вершина, расстояние]
PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[1] - b[1]);
pq.offer(new int[]{start, 0});

// k ближайших точек к началу координат — по квадрату расстояния, по убыванию (max-heap размера k)
PriorityQueue<int[]> farthest = new PriorityQueue<>(
    (a, b) -> (b[0]*b[0] + b[1]*b[1]) - (a[0]*a[0] + a[1]*a[1])
);
```

## Set

- `HashSet`: `add`, `contains`, `remove` — O(1).
- `TreeSet` (когда нужен порядок/ближайший элемент): `floor(x)`, `ceiling(x)`, `higher(x)`, `lower(x)`, `first()`,
  `last()`.

```
TreeSet<Integer> ts = new TreeSet<>(List.of(1, 5, 9, 14));
ts.floor(7);    // 5  — наибольший элемент <= 7
ts.ceiling(7);  // 9  — наименьший элемент >= 7
```

## Map (в основном HashMap)

```
// getOrDefault — вместо ручной проверки на null
int count = map.getOrDefault(key, 0);

// merge — подсчёт частот в одну строку
map.merge(key, 1, Integer::sum);              // count[key] = count.getOrDefault(key,0) + 1

// compute — то же самое, но явной функцией
map.compute(key, (k, v) -> v == null ? 1 : v + 1);

// computeIfAbsent — построение adjacency list / группировки без ручного if
Map<Integer, List<Integer>> graph = new HashMap<>();
graph.computeIfAbsent(u, k -> new ArrayList<>()).add(v);
// без computeIfAbsent пришлось бы:
// if (!graph.containsKey(u)) graph.put(u, new ArrayList<>());
// graph.get(u).add(v);

// putIfAbsent — вставит, только если ключа ещё нет; в отличие от put() не перезапишет существующее значение
map.putIfAbsent(key, new ArrayList<>());
map.get(key).add(v);

// computeIfPresent — обновить значение, только если ключ уже есть
inDegree.computeIfPresent(node, (k, v) -> v - 1);
```

- Итерация: `for (Map.Entry<K,V> e : map.entrySet())`, `map.keySet()`, `map.values()`.
- `LinkedHashMap` — сохраняет порядок вставки, основа для LRU Cache (+ override `removeEldestEntry`).
- `TreeMap` — как TreeSet, но с value: `floorKey`, `ceilingKey`, `firstKey`, `lastKey`.

---

## Comparator — примеры для более сложных случаев

**Массив/пара — по первому полю, при равенстве по второму:**

```
int[][] intervals = {{1,3},{2,6},{8,10}};
Arrays.sort(intervals, (a, b) -> a[0] != b[0] ? a[0] - b[0] : a[1] - b[1]);
// то же самое через Comparator.comparingInt + thenComparingInt (безопаснее — без риска overflow на a[0]-b[0])
Arrays.sort(intervals, Comparator.comparingInt((int[] iv) -> iv[0]).thenComparingInt(iv -> iv[1]));
```

**Пользовательский класс, сортировка по нескольким полям:**

```
class Employee {
    String department;
    int salary;
    String name;
}

List<Employee> employees = ...;
employees.sort(
    Comparator.comparing((Employee e) -> e.department)      // сначала по отделу
              .thenComparing(e -> -e.salary)                 // затем по зарплате по убыванию
              .thenComparing(e -> e.name)                    // затем по имени
);

// то же по убыванию зарплаты через .reversed()
employees.sort(Comparator.comparingInt((Employee e) -> e.salary).reversed());
```

**PriorityQueue с компаратором на пользовательском классе:**

```
PriorityQueue<Employee> pq = new PriorityQueue<>(
    Comparator.comparingInt((Employee e) -> e.salary).reversed()
);
```

**Comparator для строк по длине, затем лексикографически:**

```
words.sort(Comparator.comparingInt(String::length).thenComparing(Comparator.naturalOrder()));
```

---

## Java 21+ Sequenced Collections (JEP 431)

Единый интерфейс first/last-доступа для упорядоченных коллекций. У `Deque` такие методы были и раньше — новое здесь
то, что теперь они появились и у `List`, `LinkedHashSet`, `LinkedHashMap`.

### List — старый способ vs новый

```
List<Integer> list = new ArrayList<>(List.of(1, 2, 3));

// старый способ            // новый способ (Java 21+)
list.get(0);                 list.getFirst();
list.get(list.size() - 1);   list.getLast();
list.add(0, x);               list.addFirst(x);
list.add(x);                  list.addLast(x);
list.remove(0);                list.removeFirst();
list.remove(list.size() - 1); list.removeLast();

Collections.reverse(list);    // мутирует список на месте
List<Integer> rev = list.reversed(); // НЕ мутирует — возвращает reversed-view
```

⚠️ `reversed()` возвращает представление (view), а не копию и не мутирует исходный список — это отличается от
`Collections.reverse()`, который мутирует список на месте.

### LinkedHashMap — новые методы

```
LinkedHashMap<Integer, Integer> map = new LinkedHashMap<>();
map.putFirst(1, 100);          // вставить в начало порядка (сдвигает существующий с этим ключом)
map.putLast(2, 200);
map.firstEntry();              // Map.Entry с самым "первым" по порядку вставки ключом
map.lastEntry();
map.pollFirstEntry();          // достать и удалить первую запись — удобно для LRU без ручного bookkeeping
map.pollLastEntry();
map.reversed();                // view в обратном порядке
```

### LinkedHashSet — аналогично List

```
LinkedHashSet<Integer> set = new LinkedHashSet<>(List.of(1, 2, 3));
set.getFirst();
set.getLast();
set.reversed();
```

Использовать новый API не обязательно — старые способы (`get(0)`, `get(size()-1)`) работают точно так же. Но если
видишь такой код у интервьюера/в чужом решении — не должно вызвать ступор.
