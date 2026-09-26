# Упражнения по Java Collections

Тренажёр к [JAVA_COLLECTIONS.md](JAVA_COLLECTIONS.md). Цель — чтобы методы коллекций писались **без IDE и с первого
раза**. Это напрямую бьёт по ошибкам **С** (синтаксис / API) и **Т** (тип возврата) из [PROTOCOL.md](PROTOCOL.md).

## Как заниматься

- Писать ответ в `.txt` / на бумаге, **без IDE и без автодополнения** — как на онлайн-собесе.
- Только после ответа открыть `Ответ` и проверить. Сомневаешься — прогнать в `jshell` (есть в JDK 21):
  ```
  jshell
  jshell> var d = new ArrayDeque<Integer>(); d.push(1); d.offer(2); d
  ```
- Ошибся — поставить отметку в таблице прогресса внизу и повторить блок через 3 дня.
- Один блок ≈ 15–20 минут. Весь файл — 2–3 сессии; дальше — только блоки с ошибками.

Типы упражнений:

- 🔮 **Что выведет** — предсказать результат или исключение.
- ✍️ **Напиши по памяти** — одна-три строки кода.
- 🐞 **Найди ошибку** — не скомпилируется / упадёт / даст неверный результат.
- 🧩 **Мини-задача** — 5–15 строк, паттерн из LeetCode.

Все ответы 🔮 и 🐞 проверены на OpenJDK 21.

---

## 1. List

**1.1 🔮**

``` 
List<Integer> list = new ArrayList<>(List.of(10, 20, 30, 40));
list.

remove(1);
list.

remove(Integer.valueOf(40));
        System.out.

println(list);
System.out.

println(list.indexOf(99));
```

<details><summary>Ответ</summary>

`[10, 30]` и `-1`. `remove(1)` — по **индексу** (удалил 20), `remove(Integer.valueOf(40))` — по **значению**.
`indexOf` отсутствующего элемента — `-1`, не исключение.
</details>

**1.2 🔮**

```java
List<Integer> list = List.of(1, 2, 3);
list.

add(4);
```

<details><summary>Ответ</summary>

`UnsupportedOperationException`. `List.of(...)` — неизменяемый список. Нужен изменяемый —
`new ArrayList<>(List.of(1, 2, 3))`.
</details>

**1.3 🔮**

```java
System.out.println(Arrays.asList(new int[] {
    1, 2, 3
}).

size());
```

<details><summary>Ответ</summary>

`1`. `int[]` — один объект, получился `List<int[]>` из одного элемента. `Arrays.asList` работает с
`Integer[]`, не с `int[]`.
</details>

**1.4 ✍️** Отсортировать `List<String> words` по длине **по убыванию**.

<details><summary>Ответ</summary>

```java
words.sort(Comparator.comparingInt(String::length).

reversed());
```

</details>

**1.5 ✍️** Превратить `List<Integer> list` в `int[]` (частый тип возврата на LeetCode).

<details><summary>Ответ</summary>

```java
int[] arr = list.stream().mapToInt(Integer::intValue).toArray();
```

или руками: `int[] arr = new int[list.size()]; for (int i = 0; i < arr.length; i++) arr[i] = list.get(i);`
</details>

**1.6 🐞**

```java
List<Integer> nums = new ArrayList<>(List.of(3, 1, 2));
for(
int i = 0;
i<nums.length;i++){
        System.out.

println(nums[i]);
}
```

<details><summary>Ответ</summary>

Две ошибки компиляции: у `List` — `nums.size()` (метод), не `length`; доступ — `nums.get(i)`, не `nums[i]`.
Шпаргалка: `arr.length` · `s.length()` · `list.size()`.
</details>

---

## 2. Deque (ArrayDeque)

**2.1 🔮**

```java
Deque<Integer> d = new ArrayDeque<>();
d.

push(1);
d.

push(2);
d.

offer(3);
System.out.

println(d);
System.out.

println(d.pop() +" "+d.

poll() +" "+d.

peek());
```

<details><summary>Ответ</summary>

`[2, 1, 3]` и `2 1 3`. `push` кладёт в **начало**, `offer` — в **конец**. `pop` и `poll` оба берут из начала,
`peek` смотрит начало.
</details>

**2.2 🔮** Что вернёт каждый вызов на **пустом** `ArrayDeque`: `poll()`, `peek()`, `pop()`?

<details><summary>Ответ</summary>

`poll()` → `null`, `peek()` → `null`, `pop()` → `NoSuchElementException`. Для безопасной проверки —
`isEmpty()` до `pop()`, или `poll()` + проверка на `null`.
</details>

**2.3 🔮**

```java
Deque<Integer> d = new ArrayDeque<>();
d.

offer(null);
```

<details><summary>Ответ</summary>

`NullPointerException` — `ArrayDeque` не хранит `null` (в отличие от `LinkedList`).
</details>

**2.4 ✍️** Объявить стек символов и очередь пар `[row, col]`.

<details><summary>Ответ</summary>

```java
Deque<Character> stack = new ArrayDeque<>();
Deque<int[]> queue = new ArrayDeque<>();
queue.

offer(new int[] {
    r, c
});
int[] cell = queue.poll();
```

</details>

**2.5 🧩** [20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/) — через `Deque<Character>`.

<details><summary>Ответ</summary>

```java
public boolean isValid(String s) {
    Deque<Character> stack = new ArrayDeque<>();
    for (char c : s.toCharArray()) {
        if (c == '(') stack.push(')');
        else if (c == '[') stack.push(']');
        else if (c == '{') stack.push('}');
        else if (stack.isEmpty() || stack.pop() != c) return false;
    }
    return stack.isEmpty();
}
```

Краевые случаи (К): строка из одной закрывающей скобки — `isEmpty()` до `pop()`; незакрытые — `return stack.isEmpty()`.
</details>

**2.6 🧩** [239. Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/). В шпаргалке есть
шаблон монотонного дека — **допиши**, чтобы он возвращал `int[]` с максимумами окон.

<details><summary>Ответ</summary>

```java
public int[] maxSlidingWindow(int[] nums, int k) {
    int[] res = new int[nums.length - k + 1];
    Deque<Integer> monoDeque = new ArrayDeque<>();   // индексы, значения убывают
    for (int i = 0; i < nums.length; i++) {
        while (!monoDeque.isEmpty() && nums[monoDeque.peekLast()] < nums[i]) {
            monoDeque.pollLast();
        }
        monoDeque.offerLast(i);
        if (monoDeque.peekFirst() <= i - k) {
            monoDeque.pollFirst();
        }
        if (i >= k - 1) {
            res[i - k + 1] = nums[monoDeque.peekFirst()];
        }
    }
    return res;
}
```

Ключевое: в деке **индексы**, не значения — иначе не понять, выпал ли элемент из окна.
</details>

---

## 3. PriorityQueue

**3.1 🔮**

```java
PriorityQueue<Integer> pq = new PriorityQueue<>(List.of(5, 1, 4));
System.out.

println(pq);
while(!pq.

isEmpty())System.out.

print(pq.poll() +" ");
```

<details><summary>Ответ</summary>

`[1, 5, 4]` и `1 4 5`. `toString()` и итерация показывают **внутренний порядок кучи**, не отсортированный.
Отсортированный порядок даёт только последовательный `poll()`.
</details>

**3.2 ✍️** Создать max-heap для `Integer` — двумя способами.

<details><summary>Ответ</summary>

```java
new PriorityQueue<>(Comparator.

reverseOrder());
        new PriorityQueue<>((a,b)->Integer.

compare(b, a));
```

</details>

**3.3 🐞**

```java
PriorityQueue<Integer> pq = new PriorityQueue<>((a, b) -> a - b);
pq.

offer(Integer.MIN_VALUE);
pq.

offer(1);
System.out.

println(pq.peek());   // ожидаем MIN_VALUE
```

<details><summary>Ответ</summary>

Выведет `1`. `MIN_VALUE - 1` переполняется в положительное число → компаратор считает `MIN_VALUE` больше.
Исправление: `Integer::compare` или `Comparator.naturalOrder()`. То же касается `a[1] - b[1]` в шпаргалке —
безопаснее `Comparator.comparingInt(a -> a[1])`.
</details>

**3.4 ✍️** Min-heap пар `int[]{value, index}` по `value`, при равенстве — по `index`.

<details><summary>Ответ</summary>

```java
PriorityQueue<int[]> pq = new PriorityQueue<>(
        (a, b) -> a[0] != b[0] ? Integer.compare(a[0], b[0]) : Integer.compare(a[1], b[1])
);
```

</details>

**3.5 🧩** [215. Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array/) —
min-heap размера `k`.

<details><summary>Ответ</summary>

```java
public int findKthLargest(int[] nums, int k) {
    PriorityQueue<Integer> heap = new PriorityQueue<>();
    for (int x : nums) {
        heap.offer(x);
        if (heap.size() > k) heap.poll();
    }
    return heap.peek();
}
```

O(n log k). Почему **min**-heap: в куче держим k самых больших, наименьший из них — на вершине и есть ответ.
</details>

**3.6 🧩** [347. Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/) — `HashMap` +
`PriorityQueue`, вернуть `int[]`.

<details><summary>Ответ</summary>

```java
public int[] topKFrequent(int[] nums, int k) {
    Map<Integer, Integer> freq = new HashMap<>();
    for (int x : nums) freq.merge(x, 1, Integer::sum);

    PriorityQueue<Map.Entry<Integer, Integer>> heap =
            new PriorityQueue<>(Map.Entry.comparingByValue());
    for (Map.Entry<Integer, Integer> e : freq.entrySet()) {
        heap.offer(e);
        if (heap.size() > k) heap.poll();
    }

    int[] res = new int[k];
    for (int i = 0; i < k; i++) res[i] = heap.poll().getKey();
    return res;
}
```

</details>

---

## 4. Set / TreeSet

**4.1 🔮**

```java
TreeSet<Integer> ts = new TreeSet<>(List.of(1, 5, 9, 14));
System.out.

println(ts.floor(5) +" "+ts.

higher(5) +" "+ts.

lower(1) +" "+ts.

ceiling(15));
        System.out.

println(ts.headSet(9) +" "+ts.

tailSet(9));
```

<details><summary>Ответ</summary>

`5 9 null null` и `[1, 5] [9, 14]`. `floor` / `ceiling` — **включительно**, `lower` / `higher` — **строго**.
Нет подходящего — `null`. `headSet(x)` — строго меньше, `tailSet(x)` — больше или равно.
</details>

**4.2 🐞**

```java
TreeSet<Integer> ts = new TreeSet<>(List.of(1, 5, 9));
int prev = ts.lower(1);
```

<details><summary>Ответ</summary>

`NullPointerException` при автораспаковке `null` в `int`. Принимать в `Integer` и проверять на `null`.
</details>

**4.3 ✍️** Используя возвращаемое значение `add`, за один проход проверить, есть ли в `int[] nums` дубликаты
([217](https://leetcode.com/problems/contains-duplicate/)).

<details><summary>Ответ</summary>

```java
Set<Integer> seen = new HashSet<>();
for(
int x :nums){
        if(!seen.

add(x))return true;   // add вернёт false, если элемент уже был
        }
        return false;
```

</details>

**4.4 🧩** [128. Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/) за O(n)
через `HashSet`.

<details><summary>Ответ</summary>

```java
public int longestConsecutive(int[] nums) {
    Set<Integer> set = new HashSet<>();
    for (int x : nums) set.add(x);
    int best = 0;
    for (int x : set) {
        if (set.contains(x - 1)) continue;      // x — не начало последовательности
        int len = 1;
        while (set.contains(x + len)) len++;
        best = Math.max(best, len);
    }
    return best;
}
```

Краевой случай (К): пустой массив → цикл не выполнится, вернётся `0`. Итерировать по `set`, не по `nums` —
иначе дубликаты дадут O(n²) в худшем случае.
</details>

---

## 5. Map

**5.1 ✍️** Подсчёт частот символов строки `s` в `Map<Character, Integer>` — тремя способами: `getOrDefault`,
`merge`, `compute`.

<details><summary>Ответ</summary>

```java
for(char c :s.

toCharArray())freq.

put(c, freq.getOrDefault(c, 0) +1);
        for(
char c :s.

toCharArray())freq.

merge(c, 1,Integer::sum);
for(
char c :s.

toCharArray())freq.

compute(c, (k, v) ->v ==null?1:v +1);
```

Для алфавита из 26 букв на собесе проще и быстрее `int[] cnt = new int[26]; cnt[c - 'a']++;`.
</details>

**5.2 🔮**

```java
Map<String, Integer> m = new HashMap<>();
m.

put("a",1);
m.

putIfAbsent("a",2);
m.

merge("a",10,Integer::sum);
m.

merge("b",5,Integer::sum);
m.

computeIfPresent("c",(k, v) ->v +1);
        m.

compute("d",(k, v) ->v ==null?1:v *2);
// что лежит в m?
```

<details><summary>Ответ</summary>

`{a=11, b=5, d=1}`. `putIfAbsent` не перезаписал `a`; `merge` на отсутствующем ключе просто кладёт значение;
`computeIfPresent` на отсутствующем `c` ничего не делает.
</details>

**5.3 🔮** Продолжение 5.2:

```java
m.computeIfPresent("b",(k, v) ->v -5==0?null:v -5);
        m.

merge("a",-11,(x, y) ->x +y ==0?null:x +y);
```

<details><summary>Ответ</summary>

`{d=1}`. Если функция в `compute*` / `merge` возвращает `null` — **ключ удаляется**. Удобно для счётчиков в
sliding window: счётчик дошёл до нуля — ключ исчез, и `map.size()` = число различных элементов в окне.
</details>

**5.4 🐞**

```java
Map<Character, Integer> cnt = new HashMap<>();
cnt.

put(c, cnt.get(c) +1);
```

<details><summary>Ответ</summary>

`NullPointerException` при первом появлении `c`: `get` вернул `null`, распаковка в `int` упала.
Исправление — `getOrDefault(c, 0) + 1` или `merge(c, 1, Integer::sum)`.
</details>

**5.5 🔮**

```java
Map<Character, Integer> c = new HashMap<>();
c.

put('a',200);
c.

put('b',200);
System.out.

println(c.get('a') ==c.

get('b'));
        System.out.

println(c.get('a').

equals(c.get('b')));
```

<details><summary>Ответ</summary>

`false` и `true`. `==` сравнивает ссылки; `Integer` кэшируется только в диапазоне −128…127. Типичный баг в
«сравнить две частотные мапы» (например, [567](https://leetcode.com/problems/permutation-in-string/)).
</details>

**5.6 🐞**

```java
for(Integer key :map.

keySet()){
        if(map.

get(key) ==0)map.

remove(key);
}
```

<details><summary>Ответ</summary>

Удаление из мапы во время for-each по ней — `ConcurrentModificationException` (fail-fast, срабатывает не
всегда, но рассчитывать на это нельзя). Правильно:

```java
map.entrySet().

removeIf(e ->e.

getValue() ==0);
```

</details>

**5.7 ✍️** Найти ключ с максимальным значением в `Map<String, Integer>`.

<details><summary>Ответ</summary>

```java
String best = null;
int max = Integer.MIN_VALUE;
for(
Map.Entry<String, Integer> e :map.

entrySet()){
        if(e.

getValue() >max){
max =e.

getValue();

best =e.

getKey();
    }
            }
```

Однострочник: `Collections.max(map.entrySet(), Map.Entry.comparingByValue()).getKey()`.
</details>

**5.8 🧩** [49. Group Anagrams](https://leetcode.com/problems/group-anagrams/) — через `computeIfAbsent`.
Тип возврата — `List<List<String>>`.

<details><summary>Ответ</summary>

```java
public List<List<String>> groupAnagrams(String[] strs) {
    Map<String, List<String>> groups = new HashMap<>();
    for (String s : strs) {
        char[] chars = s.toCharArray();
        Arrays.sort(chars);
        groups.computeIfAbsent(new String(chars), k -> new ArrayList<>()).add(s);
    }
    return new ArrayList<>(groups.values());
}
```

Т: `groups.values()` — это `Collection`, не `List`; обернуть в `new ArrayList<>(...)`.
</details>

**5.9 ✍️** Построить список смежности неориентированного графа из `int[][] edges` в
`Map<Integer, List<Integer>>`.

<details><summary>Ответ</summary>

```java
Map<Integer, List<Integer>> graph = new HashMap<>();
for(
int[] e :edges){
        graph.

computeIfAbsent(e[0], k ->new ArrayList<>()).

add(e[1]);
    graph.

computeIfAbsent(e[1], k ->new ArrayList<>()).

add(e[0]);
}
// соседи вершины без NPE для изолированных вершин:
List<Integer> nbrs = graph.getOrDefault(v, List.of());
```

</details>

**5.10 🧩** [729. My Calendar I](https://leetcode.com/problems/my-calendar-i/) — `TreeMap<start, end>`,
`floorKey` / `ceilingKey`.

<details><summary>Ответ</summary>

```java
class MyCalendar {
    private final TreeMap<Integer, Integer> booked = new TreeMap<>();

    public boolean book(int start, int end) {
        Integer prev = booked.floorKey(start);      // ближайшее начало <= start
        Integer next = booked.ceilingKey(start);    // ближайшее начало >= start
        if (prev != null && booked.get(prev) > start) return false;
        if (next != null && next < end) return false;
        booked.put(start, end);
        return true;
    }
}
```

`floorKey` / `ceilingKey` возвращают `Integer` и могут быть `null` — не `int` (см. 4.2).
</details>

**5.11 🧩** [146. LRU Cache](https://leetcode.com/problems/lru-cache/) на `LinkedHashMap`.

<details><summary>Ответ</summary>

```java
class LRUCache extends LinkedHashMap<Integer, Integer> {
    private final int capacity;

    public LRUCache(int capacity) {
        super(capacity, 0.75f, true);   // true = порядок доступа, а не вставки
        this.capacity = capacity;
    }

    public int get(int key) {
        return getOrDefault(key, -1);
    }

    public void put(int key, int value) {
        super.put(key, value);
    }

    @Override
    protected boolean removeEldestEntry(Map.Entry<Integer, Integer> eldest) {
        return size() > capacity;
    }
}
```

Главная ловушка — третий аргумент конструктора `true`. Без него порядок — по вставке, и `get` не обновляет
«свежесть». На собесе могут попросить реализацию на HashMap + двусвязном списке — эту версию стоит знать как
первый ответ, а не как единственный.
</details>

---

## 6. Comparator

**6.1 ✍️** Отсортировать `int[][] intervals` по началу по возрастанию, при равенстве — по концу **по убыванию**.

<details><summary>Ответ</summary>

```java
Arrays.sort(intervals, (a, b) ->a[0]!=b[0]
        ?Integer.

compare(a[0], b[0])
        :Integer.

compare(b[1], a[1]));
```

</details>

**6.2 🐞** Почему не компилируется и как починить?

```java
Arrays.sort(intervals, Comparator.comparingInt(x ->x[0]).

thenComparingInt(x ->x[1]));
```

<details><summary>Ответ</summary>

`error: array required, but Object found`. В цепочке `.thenComparingInt` Java не выводит тип `x` из контекста
и считает его `Object`. Без цепочки (`Comparator.comparingInt(x -> x[0])`) компилируется. Исправление — явный
тип в первой лямбде: `Comparator.comparingInt((int[] x) -> x[0]).thenComparingInt(x -> x[1])`.
</details>

**6.3 🐞**

```java
int[] arr = {3, 1, 2};
Arrays.

sort(arr, Collections.reverseOrder());
```

<details><summary>Ответ</summary>

Не компилируется: компаратор работает только с объектами, а `int[]` — примитивы. Варианты: `Integer[]`, или
`Arrays.sort(arr)` + разворот вручную, или
`Arrays.stream(arr).boxed().sorted(Comparator.reverseOrder()).mapToInt(Integer::intValue).toArray()`.
</details>

**6.4 🔮**

```java
List<String> w = new ArrayList<>(List.of("bb", "a", "ccc", "aa"));
w.

sort(Comparator.comparingInt(String::length)
        .

thenComparing(Comparator.naturalOrder())
        .

reversed());
        System.out.

println(w);
```

<details><summary>Ответ</summary>

`[ccc, bb, aa, a]`. `.reversed()` в конце разворачивает **всю цепочку**, включая алфавитный порядок
(`bb` перед `aa`). Если нужно «длина по убыванию, но буквы по возрастанию» —
`Comparator.comparingInt(String::length).reversed().thenComparing(Comparator.naturalOrder())`.
</details>

**6.5 ✍️** Отсортировать `List<Employee>` по отделу, затем по зарплате по убыванию, затем по имени — без
`-e.salary` (без риска переполнения и лишней упаковки).

<details><summary>Ответ</summary>

```java
employees.sort(Comparator.comparing((Employee e) ->e.department)
        .

thenComparing(e ->e.salary,Comparator.

reverseOrder())
        .

thenComparing(e ->e.name));
```

</details>

---

## 7. Sequenced Collections (Java 21) и StringBuilder

**7.1 🔮**

```java
List<Integer> list = new ArrayList<>(List.of(1, 2, 3));
List<Integer> rev = list.reversed();
list.

add(4);
System.out.

println(rev);
```

<details><summary>Ответ</summary>

`[4, 3, 2, 1]`. `reversed()` возвращает **представление** — изменения исходного списка видны через него.
</details>

**7.2 🔮** Что выбросит каждая строка?

```java
List.of().

getFirst();
new ArrayList<Integer>().

get(0);
```

<details><summary>Ответ</summary>

`NoSuchElementException` и `IndexOutOfBoundsException`. Разные исключения на один и тот же «пустой» случай.
</details>

**7.3 🐞** Ошибка из собственного решения задачи 67:

```java
StringBuilder result = new StringBuilder("001");
result.

reversed();
return result.

toString();
```

<details><summary>Ответ</summary>

Не компилируется: у `StringBuilder` нет `reversed()` — это метод `List` / `Deque` / `LinkedHashMap` из Java 21.
У `StringBuilder` — `reverse()`, который **мутирует** билдер и возвращает `this`:
`return result.reverse().toString();`.
</details>

**7.4 ✍️** Из `LinkedHashMap<Integer, Integer> map` достать и удалить самую старую запись — Java 21 и
классическим способом.

<details><summary>Ответ</summary>

```java
Map.Entry<Integer, Integer> e = map.pollFirstEntry();          // Java 21

Integer oldest = map.keySet().iterator().next();               // классический
map.

remove(oldest);
```

</details>

---

## 8. Сборка: какую коллекцию выбрать

Для каждого пункта назвать коллекцию и ключевые методы (устно, 30 секунд на пункт).

1. Проверить, встречалось ли число раньше.
2. Обработать клетки сетки в порядке BFS.
3. Держать 3 наибольших числа из потока.
4. Для каждого числа найти ближайшее большее среди уже встреченных.
5. Скобочная последовательность.
6. Кэш на N последних использованных ключей.
7. Сгруппировать слова по первой букве с сохранением порядка появления групп.
8. Максимум в скользящем окне.

<details><summary>Ответ</summary>

1. `HashSet` — `add` / `contains`.
2. `ArrayDeque<int[]>` как очередь — `offer` / `poll`.
3. `PriorityQueue` (min-heap размера 3) — `offer`, `poll` при `size() > 3`.
4. `TreeSet` — `higher(x)`.
5. `ArrayDeque` как стек — `push` / `pop` / `isEmpty`.
6. `LinkedHashMap` с `accessOrder = true` + `removeEldestEntry`.
7. `LinkedHashMap<Character, List<String>>` + `computeIfAbsent`.
8. `ArrayDeque` индексов как монотонный дек — `offerLast` / `pollLast` / `peekFirst` / `pollFirst`.

</details>

---

## Прогресс

Отмечать дату и число ошибок в блоке. Блок с ошибками — повторить через 3 дня, затем через 2 недели.

| Блок               | Заход 1 | Заход 2 | Заход 3 |
|:-------------------|:-------:|:-------:|:-------:|
| 1. List            |         |         |         |
| 2. Deque           |         |         |         |
| 3. PriorityQueue   |         |         |         |
| 4. Set / TreeSet   |         |         |         |
| 5. Map             |         |         |         |
| 6. Comparator      |         |         |         |
| 7. Sequenced / SB  |         |         |         |
| 8. Выбор коллекции |         |         |         |
