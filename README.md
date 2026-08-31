# leetcode-three

# leetcode-next

https://github.com/Overhellz/leetcode-next

---

# Leetcode Badges

## Top Interview 150

https://leetcode.com/studyplan/top-interview-150/

## Top 100 Liked

https://leetcode.com/studyplan/top-100-liked/

## LeetCode 75

https://leetcode.com/studyplan/leetcode-75/

---

| Retention | Description                                                         |
|:---------:|:--------------------------------------------------------------------|
|     5     | Решено самостоятельно, в пределах времени.                          |
|     4     | Решено самостоятельно, но слишком медленно / незначительные ошибки. |
|     3     | Вспомнил алгоритм, но в коде были ошибки / нужны были подсказки.    |
|     2     | Смутно помнил тему, не смог решить.                                 |
|     1     | Полный провал (не распознал задачу).                                |

---

### Порядок прохождения (линейно, без веток)

1. **Array / String** — стартовая точка — работа с базовым контейнером без вспомогательных структур
2. **Two Pointers** — первая техника поверх массива/строки
3. **Sliding Window** — частный случай two pointers для подотрезков
4. **Prefix Sum** — ещё одна техника над массивом, часто идёт в связке со sliding window
5. **Hash Map** — первая вспомогательная структура данных — O(1) поиск
6. **Stack, Queue** — линейные структуры LIFO/FIFO
7. **Monotonic Stack** — прямое расширение техники Stack
8. **Binary Search** — самостоятельная техника поиска, база для многих задач дальше (в т.ч. Dijkstra, DP)
9. **Intervals** — сортировка + two pointers/greedy над отрезками
10. **Linked List** — первая нелинейная по памяти структура
11. **Binary Tree DFS** — рекурсия на деревьях — фундамент для BST/BFS/Trie/Backtracking/Graph DFS
12. **Binary Search Tree (BST)** — дерево + инвариант сортировки
13. **Binary Tree BFS** — обход дерева через очередь (после того как Stack/Queue уже пройдены)
14. **Trie** — специализированное дерево над строками
15. **Heap / Priority Queue** — нужна до графовых задач — используется в Dijkstra
16. **Graph General** — деревья — частный случай графов, логично идти следом
17. **Graph DFS** — перенос DFS с деревьев на графы
18. **Graph BFS** — перенос BFS с деревьев на графы
19. **Topological Sort** — надстройка над Graph DFS/BFS
20. **Dijkstra** — graph BFS + heap, поэтому идёт последним в графовом блоке
21. **Backtracking** — рекурсия/DFS, но уже с перебором и откатом состояния
22. **Divide & Conquer** — ещё один рекурсивный паттерн, соседствует с backtracking
23. **Dynamic Programming** — рекурсия + мемоизация — логичное продолжение backtracking/divide & conquer
24. **Greedy** — часто разбирается в противовес DP на одних и тех же задачах (интервалы, расписания)
25. **Bit Manipulation** — самостоятельная техника, невысокий приоритет
26. **Design / OOP** — синтез уже пройденных структур (stack, hashmap, linked list, heap)
27. **Math / Simulation** — низкоприоритетные точечные задачи
28. **SQL** — отдельный навык, не про алгоритмы — логично закрывать после всей алгоритмической части

---

**Колонки-метки:**

- **Yandex** / **Freq %** — встречается ли задача в подборке компанийского тега Yandex на LeetCode, и с какой частотой.
- **TP150** — входит в официальный study plan [Top Interview 150](https://leetcode.com/studyplan/top-interview-150/) (
  150 задач).
- **LC75** — входит в [LeetCode 75](https://leetcode.com/studyplan/leetcode-75/) (75 задач).
- **Top100** — входит в [Top 100 Liked Questions](https://leetcode.com/studyplan/top-100-liked/) (100 задач).

Источники и методология — в конце файла.

# 1. Array / String

| Level  | Name                                                              | Link                                                                                       | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:------------------------------------------------------------------|:-------------------------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
|  Easy  | 1768. Merge Strings Alternately                                   | https://leetcode.com/problems/merge-strings-alternately/                                   |   —    |   —    |   —   |  ✅   |   —    |           |
|  Easy  | 1071. Greatest Common Divisor of Strings                          | https://leetcode.com/problems/greatest-common-divisor-of-strings/                          |   —    |   —    |   —   |  ✅   |   —    |           |
|  Easy  | 1431. Kids With the Greatest Number of Candies                    | https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/                    |   —    |   —    |   —   |  ✅   |   —    |           |
|  Easy  | 605. Can Place Flowers                                            | https://leetcode.com/problems/can-place-flowers/                                           |   ✅    | 37.5%  |   —   |  ✅   |   —    |           |
|  Easy  | 345. Reverse Vowels of a String                                   | https://leetcode.com/problems/reverse-vowels-of-a-string/                                  |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 334. Increasing Triplet Subsequence                               | https://leetcode.com/problems/increasing-triplet-subsequence/                              |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 443. String Compression                                           | https://leetcode.com/problems/string-compression/                                          |   ✅    | 75.0%  |   —   |  ✅   |   —    |           |
|  Easy  | 228. Summary Ranges                                               | https://leetcode.com/problems/summary-ranges/                                              |   ✅    | 87.5%  |   ✅   |  —   |   —    |           |
|  Easy  | 3105. Longest Strictly Increasing or Strictly Decreasing Subarray | https://leetcode.com/problems/longest-strictly-increasing-or-strictly-decreasing-subarray/ |   ✅    | 75.0%  |   —   |  —   |   —    |           |
|  Easy  | 674. Longest Continuous Increasing Subsequence                    | https://leetcode.com/problems/longest-continuous-increasing-subsequence/                   |   ✅    | 37.5%  |   —   |  —   |   —    |           |
|  Easy  | 896. Monotonic Array                                              | https://leetcode.com/problems/monotonic-array/                                             |   ✅    | 37.5%  |   —   |  —   |   —    |           |
|  Easy  | 1572. Matrix Diagonal Sum                                         | https://leetcode.com/problems/matrix-diagonal-sum/                                         |   ✅    | 37.5%  |   —   |  —   |   —    |           |
| Medium | 36. Valid Sudoku                                                  | https://leetcode.com/problems/valid-sudoku/                                                |   ✅    | 25.0%  |   ✅   |  —   |   —    |           |
| Medium | 54. Spiral Matrix                                                 | https://leetcode.com/problems/spiral-matrix/                                               |   ✅    | 25.0%  |   ✅   |  —   |   ✅    |           |
|  Easy  | 67. Add Binary                                                    | https://leetcode.com/problems/add-binary/                                                  |   ✅    | 25.0%  |   ✅   |  —   |   —    |           |
|  Hard  | 68. Text Justification                                            | https://leetcode.com/problems/text-justification/                                          |   ✅    | 25.0%  |   ✅   |  —   |   —    |           |
|  Easy  | 169. Majority Element                                             | https://leetcode.com/problems/majority-element/                                            |   ✅    | 25.0%  |   ✅   |  —   |   ✅    |           |
|  Easy  | 1464. Maximum Product of Two Elements in an Array                 | https://leetcode.com/problems/maximum-product-of-two-elements-in-an-array/                 |   ✅    | 25.0%  |   —   |  —   |   —    |           |
| Medium | 6. Zigzag Conversion                                              | https://leetcode.com/problems/zigzag-conversion/                                           |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 12. Integer to Roman                                              | https://leetcode.com/problems/integer-to-roman/                                            |   —    |   —    |   ✅   |  —   |   —    |           |
|  Easy  | 13. Roman to Integer                                              | https://leetcode.com/problems/roman-to-integer/                                            |   —    |   —    |   ✅   |  —   |   —    |           |
|  Easy  | 14. Longest Common Prefix                                         | https://leetcode.com/problems/longest-common-prefix/                                       |   —    |   —    |   ✅   |  —   |   —    |           |
|  Easy  | 28. Find the Index of the First Occurrence in a String            | https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/          |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 31. Next Permutation                                              | https://leetcode.com/problems/next-permutation/                                            |   —    |   —    |   —   |  —   |   ✅    |           |
|  Hard  | 41. First Missing Positive                                        | https://leetcode.com/problems/first-missing-positive/                                      |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | 48. Rotate Image                                                  | https://leetcode.com/problems/rotate-image/                                                |   —    |   —    |   ✅   |  —   |   ✅    |           |
|  Easy  | 58. Length of Last Word                                           | https://leetcode.com/problems/length-of-last-word/                                         |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 73. Set Matrix Zeroes                                             | https://leetcode.com/problems/set-matrix-zeroes/                                           |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 75. Sort Colors                                                   | https://leetcode.com/problems/sort-colors/                                                 |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | 80. Remove Duplicates from Sorted Array II                        | https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/                      |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 122. Best Time to Buy and Sell Stock II                           | https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/                          |   —    |   —    |   ✅   |  —   |   —    |           |
|  Hard  | 135. Candy                                                        | https://leetcode.com/problems/candy/                                                       |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 151. Reverse Words in a String                                    | https://leetcode.com/problems/reverse-words-in-a-string/                                   |   —    |   —    |   ✅   |  ✅   |   —    |           |
| Medium | 189. Rotate Array                                                 | https://leetcode.com/problems/rotate-array/                                                |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 240. Search a 2D Matrix II                                        | https://leetcode.com/problems/search-a-2d-matrix-ii/                                       |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | 274. H-Index                                                      | https://leetcode.com/problems/h-index/                                                     |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 287. Find the Duplicate Number                                    | https://leetcode.com/problems/find-the-duplicate-number/                                   |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | 289. Game of Life                                                 | https://leetcode.com/problems/game-of-life/                                                |   —    |   —    |   ✅   |  —   |   —    |           |

# 2. Two Pointers

| Level  | Name                                           | Link                                                                    | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:-----------------------------------------------|:------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
|  Easy  | 283. Move Zeroes                               | https://leetcode.com/problems/move-zeroes/                              |   ✅    | 75.0%  |   —   |  ✅   |   ✅    |           |
| Medium | 1679. Max Number of K-Sum Pairs                | https://leetcode.com/problems/max-number-of-k-sum-pairs/                |   —    |   —    |   —   |  ✅   |   —    |           |
|  Easy  | 344. Reverse String                            | https://leetcode.com/problems/reverse-string/                           |   —    |   —    |   —   |  —   |   —    |           |
|  Easy  | 977. Squares of a Sorted Array                 | https://leetcode.com/problems/squares-of-a-sorted-array/                |   ✅    | 62.5%  |   —   |  —   |   —    |           |
|  Easy  | 844. Backspace String Compare                  | https://leetcode.com/problems/backspace-string-compare/                 |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 18. 4Sum                                       | https://leetcode.com/problems/4sum/                                     |   ✅    | 37.5%  |   —   |  —   |   —    |           |
| Medium | 658. Find K Closest Elements                   | https://leetcode.com/problems/find-k-closest-elements/                  |   ✅    | 87.5%  |   —   |  —   |   —    |           |
|  Easy  | 125. Valid Palindrome                          | https://leetcode.com/problems/valid-palindrome/                         |   ✅    | 75.0%  |   ✅   |  —   |   —    |           |
|  Easy  | 680. Valid Palindrome II                       | https://leetcode.com/problems/valid-palindrome-ii/                      |   ✅    | 75.0%  |   —   |  —   |   —    |           |
| Medium | 5. Longest Palindromic Substring               | https://leetcode.com/problems/longest-palindromic-substring/            |   ✅    | 75.0%  |   ✅   |  —   |   ✅    |           |
|  Easy  | 88. Merge Sorted Array                         | https://leetcode.com/problems/merge-sorted-array/                       |   ✅    | 62.5%  |   ✅   |  —   |   —    |           |
|  Easy  | 392. Is Subsequence                            | https://leetcode.com/problems/is-subsequence/                           |   ✅    | 62.5%  |   ✅   |  ✅   |   —    |           |
|  Hard  | 42. Trapping Rain Water                        | https://leetcode.com/problems/trapping-rain-water/                      |   ✅    | 62.5%  |   ✅   |  —   |   ✅    |           |
| Medium | 11. Container With Most Water                  | https://leetcode.com/problems/container-with-most-water/                |   ✅    | 50.0%  |   ✅   |  ✅   |   ✅    |           |
|  Easy  | 27. Remove Element                             | https://leetcode.com/problems/remove-element/                           |   ✅    | 50.0%  |   ✅   |  —   |   —    |           |
|  Easy  | 26. Remove Duplicates from Sorted Array        | https://leetcode.com/problems/remove-duplicates-from-sorted-array/      |   ✅    | 37.5%  |   ✅   |  —   |   —    |           |
| Medium | 1868. Product of Two Run-Length Encoded Arrays | https://leetcode.com/problems/product-of-two-run-length-encoded-arrays/ |   ✅    | 37.5%  |   —   |  —   |   —    |           |
| Medium | 167. Two Sum II - Input Array Is Sorted        | https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/         |   ✅    | 25.0%  |   ✅   |  —   |   —    |           |
|  Easy  | 2570. Merge Two 2D Arrays by Summing Values    | https://leetcode.com/problems/merge-two-2d-arrays-by-summing-values/    |   ✅    | 25.0%  |   —   |  —   |   —    |           |
| Medium | 15. 3Sum                                       | https://leetcode.com/problems/3sum/                                     |   —    |   —    |   ✅   |  —   |   ✅    |           |

# 3. Sliding Window

| Level  | Name                                                                             | Link                                                                                                      | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:---------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
|  Easy  | 643. Maximum Average Subarray I                                                  | https://leetcode.com/problems/maximum-average-subarray-i/                                                 |   ✅    | 25.0%  |   —   |  ✅   |   —    |           |
| Medium | 1004. Max Consecutive Ones III                                                   | https://leetcode.com/problems/max-consecutive-ones-iii/                                                   |   ✅    | 50.0%  |   —   |  ✅   |   —    |           |
| Medium | 1493. Longest Subarray of 1's After Deleting One Element                         | https://leetcode.com/problems/longest-subarray-of-1s-after-deleting-one-element/                          |   ✅    | 100.0% |   —   |  ✅   |   —    |           |
| Medium | 904. Fruit Into Baskets                                                          | https://leetcode.com/problems/fruit-into-baskets/                                                         |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 424. Longest Repeating Character Replacement                                     | https://leetcode.com/problems/longest-repeating-character-replacement/                                    |   ✅    | 37.5%  |   —   |  —   |   —    |           |
| Medium | 567. Permutation in String                                                       | https://leetcode.com/problems/permutation-in-string/                                                      |   ✅    | 75.0%  |   —   |  —   |   —    |           |
| Medium | 438. Find All Anagrams in a String                                               | https://leetcode.com/problems/find-all-anagrams-in-a-string/                                              |   ✅    | 75.0%  |   —   |  —   |   ✅    |           |
|  Hard  | 239. Sliding Window Maximum                                                      | https://leetcode.com/problems/sliding-window-maximum/                                                     |   ✅    | 37.5%  |   —   |  —   |   ✅    |           |
| Medium | 1456. Maximum Number of Vowels in a Substring of Given Length                    | https://leetcode.com/problems/maximum-number-of-vowels-in-a-substring-of-given-length/                    |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 3. Longest Substring Without Repeating Characters                                | https://leetcode.com/problems/longest-substring-without-repeating-characters/                             |   ✅    | 87.5%  |   ✅   |  —   |   ✅    |           |
| Medium | 340. Longest Substring with At Most K Distinct Characters                        | https://leetcode.com/problems/longest-substring-with-at-most-k-distinct-characters/                       |   ✅    | 50.0%  |   —   |  —   |   —    |           |
| Medium | 2743. Count Substrings Without Repeating Character                               | https://leetcode.com/problems/count-substrings-without-repeating-character/                               |   ✅    | 50.0%  |   —   |  —   |   —    |           |
|  Hard  | 76. Minimum Window Substring                                                     | https://leetcode.com/problems/minimum-window-substring/                                                   |   ✅    | 37.5%  |   ✅   |  —   |   ✅    |           |
|  Easy  | 485. Max Consecutive Ones                                                        | https://leetcode.com/problems/max-consecutive-ones/                                                       |   ✅    | 37.5%  |   —   |  —   |   —    |           |
| Medium | 209. Minimum Size Subarray Sum                                                   | https://leetcode.com/problems/minimum-size-subarray-sum/                                                  |   ✅    | 25.0%  |   ✅   |  —   |   —    |           |
| Medium | 395. Longest Substring with At Least K Repeating Characters                      | https://leetcode.com/problems/longest-substring-with-at-least-k-repeating-characters/                     |   ✅    | 25.0%  |   —   |  —   |   —    |           |
| Medium | 487. Max Consecutive Ones II                                                     | https://leetcode.com/problems/max-consecutive-ones-ii/                                                    |   ✅    | 25.0%  |   —   |  —   |   —    |           |
|  Hard  | 992. Subarrays with K Different Integers                                         | https://leetcode.com/problems/subarrays-with-k-different-integers/                                        |   ✅    | 25.0%  |   —   |  —   |   —    |           |
| Medium | 1438. Longest Continuous Subarray With Absolute Diff Less Than or Equal to Limit | https://leetcode.com/problems/longest-continuous-subarray-with-absolute-diff-less-than-or-equal-to-limit/ |   ✅    | 25.0%  |   —   |  —   |   —    |           |
|  Hard  | 30. Substring with Concatenation of All Words                                    | https://leetcode.com/problems/substring-with-concatenation-of-all-words/                                  |   —    |   —    |   ✅   |  —   |   —    |           |

# 4. Prefix Sum

| Level  | Name                              | Link                                                        | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:----------------------------------|:------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
|  Easy  | 303. Range Sum Query - Immutable  | https://leetcode.com/problems/range-sum-query-immutable/    |   —    |   —    |   —   |  —   |   —    |           |
|  Easy  | 724. Find Pivot Index             | https://leetcode.com/problems/find-pivot-index/             |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 560. Subarray Sum Equals K        | https://leetcode.com/problems/subarray-sum-equals-k/        |   ✅    | 75.0%  |   —   |  —   |   ✅    |           |
| Medium | 525. Contiguous Array             | https://leetcode.com/problems/contiguous-array/             |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 974. Subarray Sums Divisible by K | https://leetcode.com/problems/subarray-sums-divisible-by-k/ |   ✅    | 25.0%  |   —   |  —   |   —    |           |
| Medium | 238. Product of Array Except Self | https://leetcode.com/problems/product-of-array-except-self/ |   ✅    | 50.0%  |   ✅   |  ✅   |   ✅    |           |
| Medium | 523. Continuous Subarray Sum      | https://leetcode.com/problems/continuous-subarray-sum/      |   ✅    | 37.5%  |   —   |  —   |   —    |           |
|  Easy  | 1732. Find the Highest Altitude   | https://leetcode.com/problems/find-the-highest-altitude/    |   —    |   —    |   —   |  ✅   |   —    |           |

# 5. Hash Map

| Level  | Name                                             | Link                                                                      | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:-------------------------------------------------|:--------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
|  Easy  | 706. Design HashMap                              | https://leetcode.com/problems/design-hashmap/                             |   —    |   —    |   —   |  —   |   —    |           |
|  Easy  | 136. Single Number                               | https://leetcode.com/problems/single-number/                              |   —    |   —    |   ✅   |  ✅   |   ✅    |           |
| Medium | 49. Group Anagrams                               | https://leetcode.com/problems/group-anagrams/                             |   ✅    | 62.5%  |   ✅   |  —   |   ✅    |           |
| Medium | 454. 4Sum II                                     | https://leetcode.com/problems/4sum-ii/                                    |   —    |   —    |   —   |  —   |   —    |           |
|  Easy  | 1. Two Sum                                       | https://leetcode.com/problems/two-sum/                                    |   ✅    | 75.0%  |   ✅   |  —   |   ✅    |           |
|  Easy  | 205. Isomorphic Strings                          | https://leetcode.com/problems/isomorphic-strings/                         |   ✅    | 75.0%  |   ✅   |  —   |   —    |           |
| Medium | 356. Line Reflection                             | https://leetcode.com/problems/line-reflection/                            |   ✅    | 75.0%  |   —   |  —   |   —    |           |
| Medium | 2657. Find the Prefix Common Array of Two Arrays | https://leetcode.com/problems/find-the-prefix-common-array-of-two-arrays/ |   ✅    | 62.5%  |   —   |  —   |   —    |           |
|  Easy  | 349. Intersection of Two Arrays                  | https://leetcode.com/problems/intersection-of-two-arrays/                 |   ✅    | 37.5%  |   —   |  —   |   —    |           |
|  Easy  | 350. Intersection of Two Arrays II               | https://leetcode.com/problems/intersection-of-two-arrays-ii/              |   ✅    | 37.5%  |   —   |  —   |   —    |           |
|  Easy  | 387. First Unique Character in a String          | https://leetcode.com/problems/first-unique-character-in-a-string/         |   ✅    | 37.5%  |   —   |  —   |   —    |           |
|  Easy  | 242. Valid Anagram                               | https://leetcode.com/problems/valid-anagram/                              |   ✅    | 25.0%  |   ✅   |  —   |   —    |           |
|  Easy  | 771. Jewels and Stones                           | https://leetcode.com/problems/jewels-and-stones/                          |   ✅    | 25.0%  |   —   |  —   |   —    |           |
|  Easy  | 1496. Path Crossing                              | https://leetcode.com/problems/path-crossing/                              |   ✅    | 25.0%  |   —   |  —   |   —    |           |
|  Easy  | 2215. Find the Difference of Two Arrays          | https://leetcode.com/problems/find-the-difference-of-two-arrays/          |   ✅    | 25.0%  |   —   |  ✅   |   —    |           |
|  Easy  | 2956. Find Common Elements Between Two Arrays    | https://leetcode.com/problems/find-common-elements-between-two-arrays/    |   ✅    | 25.0%  |   —   |  —   |   —    |           |
| Medium | 128. Longest Consecutive Sequence                | https://leetcode.com/problems/longest-consecutive-sequence/               |   —    |   —    |   ✅   |  —   |   ✅    |           |
|  Easy  | 202. Happy Number                                | https://leetcode.com/problems/happy-number/                               |   —    |   —    |   ✅   |  —   |   —    |           |
|  Easy  | 219. Contains Duplicate II                       | https://leetcode.com/problems/contains-duplicate-ii/                      |   —    |   —    |   ✅   |  —   |   —    |           |
|  Easy  | 290. Word Pattern                                | https://leetcode.com/problems/word-pattern/                               |   —    |   —    |   ✅   |  —   |   —    |           |
|  Easy  | 383. Ransom Note                                 | https://leetcode.com/problems/ransom-note/                                |   —    |   —    |   ✅   |  —   |   —    |           |
|  Easy  | 1207. Unique Number of Occurrences               | https://leetcode.com/problems/unique-number-of-occurrences/               |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 1657. Determine if Two Strings Are Close         | https://leetcode.com/problems/determine-if-two-strings-are-close/         |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 2352. Equal Row and Column Pairs                 | https://leetcode.com/problems/equal-row-and-column-pairs/                 |   —    |   —    |   —   |  ✅   |   —    |           |

# 6. Stack, Queue

| Level  | Name                                           | Link                                                                    | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:-----------------------------------------------|:------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
|  Easy  | 1047. Remove All Adjacent Duplicates In String | https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string/ |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 2390. Removing Stars From a String             | https://leetcode.com/problems/removing-stars-from-a-string/             |   —    |   —    |   —   |  ✅   |   —    |           |
|  Easy  | 933. Number of Recent Calls                    | https://leetcode.com/problems/number-of-recent-calls/                   |   ✅    | 50.0%  |   —   |  ✅   |   —    |           |
|  Easy  | 20. Valid Parentheses                          | https://leetcode.com/problems/valid-parentheses/                        |   ✅    | 62.5%  |   ✅   |  —   |   ✅    |           |
|  Easy  | 232. Implement Queue using Stacks              | https://leetcode.com/problems/implement-queue-using-stacks/             |   ✅    | 37.5%  |   —   |  —   |   —    |           |
|  Easy  | 225. Implement Stack using Queues              | https://leetcode.com/problems/implement-stack-using-queues/             |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 71. Simplify Path                              | https://leetcode.com/problems/simplify-path/                            |   ✅    | 37.5%  |   ✅   |  —   |   —    |           |
| Medium | 155. Min Stack                                 | https://leetcode.com/problems/min-stack/                                |   ✅    | 62.5%  |   ✅   |  —   |   ✅    |           |
| Medium | 227. Basic Calculator II                       | https://leetcode.com/problems/basic-calculator-ii/                      |   ✅    | 37.5%  |   —   |  —   |   —    |           |
| Medium | 150. Evaluate Reverse Polish Notation          | https://leetcode.com/problems/evaluate-reverse-polish-notation/         |   ✅    | 25.0%  |   ✅   |  —   |   —    |           |
|  Hard  | 224. Basic Calculator                          | https://leetcode.com/problems/basic-calculator/                         |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 394. Decode String                             | https://leetcode.com/problems/decode-string/                            |   —    |   —    |   —   |  ✅   |   ✅    |           |
| Medium | 649. Dota2 Senate                              | https://leetcode.com/problems/dota2-senate/                             |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 735. Asteroid Collision                        | https://leetcode.com/problems/asteroid-collision/                       |   —    |   —    |   —   |  ✅   |   —    |           |

# 7. Monotonic Stack

| Level  | Name                               | Link                                                          | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:-----------------------------------|:--------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 739. Daily Temperatures            | https://leetcode.com/problems/daily-temperatures/             |   ✅    | 25.0%  |   —   |  ✅   |   ✅    |           |
|  Hard  | 42. Trapping Rain Water            | https://leetcode.com/problems/trapping-rain-water/            |   ✅    | 62.5%  |   ✅   |  —   |   ✅    |           |
|  Hard  | 84. Largest Rectangle in Histogram | https://leetcode.com/problems/largest-rectangle-in-histogram/ |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | Next Greater Element I             | https://leetcode.com/problems/next-greater-element-i/         |   —    |   —    |   —   |  —   |   —    |           |

# 8. Binary Search

| Level  | Name                                                        | Link                                                                                   | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:------------------------------------------------------------|:---------------------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
|  Easy  | 704. Binary Search                                          | https://leetcode.com/problems/binary-search/                                           |   ✅    | 25.0%  |   —   |  —   |   —    | 5         |
|  Easy  | 35. Search Insert Position                                  | https://leetcode.com/problems/search-insert-position/                                  |   ✅    | 25.0%  |   ✅   |  —   |   ✅    | 3         |
| Medium | 34. Find First and Last Position of Element in Sorted Array | https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/ |   —    |   —    |   ✅   |  —   |   ✅    | 2         |
| Medium | 74. Search a 2D Matrix                                      | https://leetcode.com/problems/search-a-2d-matrix/                                      |   ✅    | 25.0%  |   ✅   |  —   |   ✅    | 3         |
| Medium | 153. Find Minimum in Rotated Sorted Array                   | https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/                    |   ✅    | 37.5%  |   ✅   |  —   |   ✅    | 2         |
| Medium | 33. Search in Rotated Sorted Array                          | https://leetcode.com/problems/search-in-rotated-sorted-array/                          |   ✅    | 50.0%  |   ✅   |  —   |   ✅    | 2         |
| Medium | 162. Find Peak Element                                      | https://leetcode.com/problems/find-peak-element/                                       |   —    |   —    |   ✅   |  ✅   |   —    | 2         |
| Medium | 875. Koko Eating Bananas                                    | https://leetcode.com/problems/koko-eating-bananas/                                     |   —    |   —    |   —   |  ✅   |   —    | 2         |
| Medium | 658. Find K Closest Elements                                | https://leetcode.com/problems/find-k-closest-elements/                                 |   ✅    | 87.5%  |   —   |  —   |   —    |           |
|  Hard  | 4. Median of Two Sorted Arrays                              | https://leetcode.com/problems/median-of-two-sorted-arrays/                             |   ✅    | 50.0%  |   ✅   |  —   |   ✅    |           |
| Medium | 300. Longest Increasing Subsequence                         | https://leetcode.com/problems/longest-increasing-subsequence/                          |   ✅    | 37.5%  |   ✅   |  —   |   ✅    |           |
|  Easy  | 374. Guess Number Higher or Lower                           | https://leetcode.com/problems/guess-number-higher-or-lower/                            |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 2300. Successful Pairs of Spells and Potions                | https://leetcode.com/problems/successful-pairs-of-spells-and-potions/                  |   —    |   —    |   —   |  ✅   |   —    |           |

# 9. Intervals

|   Level   | Name                                                 | Link                                                                          | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:---------:|:-----------------------------------------------------|:------------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
|  Medium   | 56. Merge Intervals                                  | https://leetcode.com/problems/merge-intervals/                                |   ✅    | 75.0%  |   ✅   |  —   |   ✅    |           |
|  Medium   | 57. Insert Interval                                  | https://leetcode.com/problems/insert-interval/                                |   —    |   —    |   ✅   |  —   |   —    |           |
|  Medium   | 435. Non-overlapping Intervals                       | https://leetcode.com/problems/non-overlapping-intervals/                      |   —    |   —    |   —   |  ✅   |   —    |           |
|  Medium   | 452. Minimum Number of Arrows to Burst Balloons      | https://leetcode.com/problems/minimum-number-of-arrows-to-burst-balloons/     |   —    |   —    |   ✅   |  ✅   |   —    |           |
|  Medium   | 986. Interval List Intersections                     | https://leetcode.com/problems/interval-list-intersections/                    |   ✅    | 62.5%  |   —   |  —   |   —    |           |
| Medium(-) | 763. Partition Labels                                | https://leetcode.com/problems/partition-labels/                               |   —    |   —    |   —   |  —   |   ✅    |           |
|  Medium   | 2406. Divide Intervals Into Minimum Number of Groups | https://leetcode.com/problems/divide-intervals-into-minimum-number-of-groups/ |   —    |   —    |   —   |  —   |   —    |           |
|  Medium   | 1288. Remove Covered Intervals                       | https://leetcode.com/problems/remove-covered-intervals/                       |   —    |   —    |   —   |  —   |   —    |           |
|  Medium   | 1229. Meeting Scheduler                              | https://leetcode.com/problems/meeting-scheduler/                              |   ✅    | 25.0%  |   —   |  —   |   —    |           |

# 10. Linked List

| Level  | Name                                          | Link                                                                   | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:----------------------------------------------|:-----------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 707. Design Linked List                       | https://leetcode.com/problems/design-linked-list/                      |   —    |   —    |   —   |  —   |   —    |           |
|  Easy  | 876. Middle of the Linked List                | https://leetcode.com/problems/middle-of-the-linked-list/               |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 2095. Delete the Middle Node of a Linked List | https://leetcode.com/problems/delete-the-middle-node-of-a-linked-list/ |   —    |   —    |   —   |  ✅   |   —    |           |
|  Easy  | 206. Reverse Linked List                      | https://leetcode.com/problems/reverse-linked-list/                     |   ✅    | 37.5%  |   —   |  ✅   |   ✅    |           |
|  Easy  | 234. Palindrome Linked List                   | https://leetcode.com/problems/palindrome-linked-list/                  |   ✅    | 25.0%  |   —   |  —   |   ✅    |           |
|  Easy  | 83. Remove Duplicates from Sorted List        | https://leetcode.com/problems/remove-duplicates-from-sorted-list/      |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 19. Remove Nth Node From End of List          | https://leetcode.com/problems/remove-nth-node-from-end-of-list/        |   ✅    | 37.5%  |   ✅   |  —   |   ✅    |           |
| Medium | 24. Swap Nodes in Pairs                       | https://leetcode.com/problems/swap-nodes-in-pairs/                     |   ✅    | 25.0%  |   —   |  —   |   ✅    |           |
|  Easy  | 21. Merge Two Sorted Lists                    | https://leetcode.com/problems/merge-two-sorted-lists/                  |   ✅    | 62.5%  |   ✅   |  —   |   ✅    |           |
|  Easy  | 141. Linked List Cycle                        | https://leetcode.com/problems/linked-list-cycle/                       |   ✅    | 37.5%  |   ✅   |  —   |   ✅    |           |
| Medium | 146. LRU Cache                                | https://leetcode.com/problems/lru-cache/                               |   ✅    | 50.0%  |   ✅   |  —   |   ✅    |           |
| Medium | 142. Linked List Cycle II                     | https://leetcode.com/problems/linked-list-cycle-ii/                    |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | 2. Add Two Numbers                            | https://leetcode.com/problems/add-two-numbers/                         |   ✅    | 37.5%  |   ✅   |  —   |   ✅    |           |
| Medium | 143. Reorder List                             | https://leetcode.com/problems/reorder-list/                            |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 138. Copy List with Random Pointer            | https://leetcode.com/problems/copy-list-with-random-pointer/           |   —    |   —    |   ✅   |  —   |   ✅    |           |
|  Hard  | 25. Reverse Nodes in k-Group                  | https://leetcode.com/problems/reverse-nodes-in-k-group/                |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 61. Rotate List                               | https://leetcode.com/problems/rotate-list/                             |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 82. Remove Duplicates from Sorted List II     | https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/   |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 86. Partition List                            | https://leetcode.com/problems/partition-list/                          |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 92. Reverse Linked List II                    | https://leetcode.com/problems/reverse-linked-list-ii/                  |   —    |   —    |   ✅   |  —   |   —    |           |
|  Easy  | 160. Intersection of Two Linked Lists         | https://leetcode.com/problems/intersection-of-two-linked-lists/        |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | 328. Odd Even Linked List                     | https://leetcode.com/problems/odd-even-linked-list/                    |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 2130. Maximum Twin Sum of a Linked List       | https://leetcode.com/problems/maximum-twin-sum-of-a-linked-list/       |   —    |   —    |   —   |  ✅   |   —    |           |

# 11. Binary Tree DFS

| Level  | Name                                                            | Link                                                                                      | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:----------------------------------------------------------------|:------------------------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
|  Easy  | 104. Maximum Depth of Binary Tree                               | https://leetcode.com/problems/maximum-depth-of-binary-tree/                               |   —    |   —    |   ✅   |  ✅   |   ✅    |           |
|  Easy  | 226. Invert Binary Tree                                         | https://leetcode.com/problems/invert-binary-tree/                                         |   —    |   —    |   ✅   |  —   |   ✅    |           |
|  Easy  | 100. Same Tree                                                  | https://leetcode.com/problems/same-tree/                                                  |   —    |   —    |   ✅   |  —   |   —    |           |
|  Easy  | 101. Symmetric Tree                                             | https://leetcode.com/problems/symmetric-tree/                                             |   ✅    | 50.0%  |   ✅   |  —   |   ✅    |           |
|  Easy  | 112. Path Sum                                                   | https://leetcode.com/problems/path-sum/                                                   |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 543. Diameter of Binary Tree                                    | https://leetcode.com/problems/diameter-of-binary-tree/                                    |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | 236. Lowest Common Ancestor of a Binary Tree                    | https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/                    |   ✅    | 50.0%  |   ✅   |  ✅   |   ✅    |           |
| Medium | 105. Construct Binary Tree from Preorder and Inorder Traversal  | https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/  |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 114. Flatten Binary Tree to Linked List                         | https://leetcode.com/problems/flatten-binary-tree-to-linked-list/                         |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 652. Find Duplicate Subtrees                                    | https://leetcode.com/problems/find-duplicate-subtrees/                                    |   ✅    | 62.5%  |   —   |  —   |   —    |           |
|  Hard  | 124. Binary Tree Maximum Path Sum                               | https://leetcode.com/problems/binary-tree-maximum-path-sum/                               |   ✅    | 50.0%  |   ✅   |  —   |   ✅    |           |
| Medium | 1650. Lowest Common Ancestor of a Binary Tree III               | https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree-iii/                |   ✅    | 25.0%  |   —   |  —   |   —    |           |
|  Easy  | 94. Binary Tree Inorder Traversal                               | https://leetcode.com/problems/binary-tree-inorder-traversal/                              |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | 106. Construct Binary Tree from Inorder and Postorder Traversal | https://leetcode.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal/ |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 129. Sum Root to Leaf Numbers                                   | https://leetcode.com/problems/sum-root-to-leaf-numbers/                                   |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 222. Count Complete Tree Nodes                                  | https://leetcode.com/problems/count-complete-tree-nodes/                                  |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 437. Path Sum III                                               | https://leetcode.com/problems/path-sum-iii/                                               |   —    |   —    |   —   |  ✅   |   ✅    |           |
|  Easy  | 872. Leaf-Similar Trees                                         | https://leetcode.com/problems/leaf-similar-trees/                                         |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 1372. Longest ZigZag Path in a Binary Tree                      | https://leetcode.com/problems/longest-zigzag-path-in-a-binary-tree/                       |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 1448. Count Good Nodes in Binary Tree                           | https://leetcode.com/problems/count-good-nodes-in-binary-tree/                            |   —    |   —    |   —   |  ✅   |   —    |           |

# 12. Binary Search Tree (BST)

| Level  | Name                                                | Link                                                                          | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:----------------------------------------------------|:------------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
|  Easy  | 700. Search in a Binary Search Tree                 | https://leetcode.com/problems/search-in-a-binary-search-tree/                 |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 701. Insert into a Binary Search Tree               | https://leetcode.com/problems/insert-into-a-binary-search-tree/               |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 98. Validate Binary Search Tree                     | https://leetcode.com/problems/validate-binary-search-tree/                    |   ✅    | 25.0%  |   ✅   |  —   |   ✅    |           |
|  Easy  | 110. Balanced Binary Tree                           | https://leetcode.com/problems/balanced-binary-tree/                           |   —    |   —    |   —   |  —   |   —    |           |
|  Easy  | 108. Convert Sorted Array to Binary Search Tree     | https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/     |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 450. Delete Node in a BST                           | https://leetcode.com/problems/delete-node-in-a-bst/                           |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 230. Kth Smallest Element in a BST                  | https://leetcode.com/problems/kth-smallest-element-in-a-bst/                  |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 173. Binary Search Tree Iterator                    | https://leetcode.com/problems/binary-search-tree-iterator/                    |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 538. Convert BST to Greater Tree                    | https://leetcode.com/problems/convert-bst-to-greater-tree/                    |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 235. Lowest Common Ancestor of a Binary Search Tree | https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/ |   ✅    | 37.5%  |   —   |  —   |   —    |           |
|  Easy  | 938. Range Sum of BST                               | https://leetcode.com/problems/range-sum-of-bst/                               |   ✅    | 37.5%  |   —   |  —   |   —    |           |
|  Easy  | 530. Minimum Absolute Difference in BST             | https://leetcode.com/problems/minimum-absolute-difference-in-bst/             |   —    |   —    |   ✅   |  —   |   —    |           |

# 13. Binary Tree BFS

| Level  | Name                                                | Link                                                                          | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:----------------------------------------------------|:------------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 102. Binary Tree Level Order Traversal              | https://leetcode.com/problems/binary-tree-level-order-traversal/              |   ✅    | 37.5%  |   ✅   |  —   |   ✅    |           |
| Medium | 515. Find Largest Value in Each Tree Row            | https://leetcode.com/problems/find-largest-value-in-each-tree-row/            |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 199. Binary Tree Right Side View                    | https://leetcode.com/problems/binary-tree-right-side-view/                    |   ✅    | 62.5%  |   ✅   |  ✅   |   ✅    |           |
| Medium | 117. Populating Next Right Pointers in Each Node II | https://leetcode.com/problems/populating-next-right-pointers-in-each-node-ii/ |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 236. Lowest Common Ancestor of a Binary Tree        | https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/        |   ✅    | 50.0%  |   ✅   |  ✅   |   ✅    |           |
| Medium | 1325. Delete Leaves With a Given Value              | https://leetcode.com/problems/delete-leaves-with-a-given-value/               |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 1302. Deepest Leaves Sum                            | https://leetcode.com/problems/deepest-leaves-sum/                             |   —    |   —    |   —   |  —   |   —    |           |
|  Easy  | 543. Diameter of Binary Tree                        | https://leetcode.com/problems/diameter-of-binary-tree/                        |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | 103. Binary Tree Zigzag Level Order Traversal       | https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/       |   ✅    | 37.5%  |   ✅   |  —   |   —    |           |
|  Easy  | 637. Average of Levels in Binary Tree               | https://leetcode.com/problems/average-of-levels-in-binary-tree/               |   —    |   —    |   ✅   |  —   |   —    | -         |
| Medium | 513. Find Bottom Left Tree Value                    | https://leetcode.com/problems/find-bottom-left-tree-value/                    |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 116. Populating Next Right Pointers in Each Node    | https://leetcode.com/problems/populating-next-right-pointers-in-each-node/    |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 987. Vertical Order Traversal of a Binary Tree      | https://leetcode.com/problems/vertical-order-traversal-of-a-binary-tree/      |   —    |   —    |   —   |  —   |   —    | 1         |
| Medium | 1161. Maximum Level Sum of a Binary Tree            | https://leetcode.com/problems/maximum-level-sum-of-a-binary-tree/             |   —    |   —    |   —   |  ✅   |   —    |           |

# 14. Trie

| Level  | Name                                            | Link                                                                      | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:------------------------------------------------|:--------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 208. Implement Trie (Prefix Tree)               | https://leetcode.com/problems/implement-trie-prefix-tree/                 |   —    |   —    |   ✅   |  ✅   |   ✅    |           |
| Medium | 1268. Search Suggestions System                 | https://leetcode.com/problems/search-suggestions-system/                  |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 211. Design Add and Search Words Data Structure | https://leetcode.com/problems/design-add-and-search-words-data-structure/ |   —    |   —    |   ✅   |  —   |   —    |           |
|  Hard  | 212. Word Search II                             | https://leetcode.com/problems/word-search-ii/                             |   —    |   —    |   ✅   |  —   |   —    |           |

# 15. Heap / Priority Queue

| Level  | Name                                      | Link                                                               | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:------------------------------------------|:-------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 215. Kth Largest Element in an Array      | https://leetcode.com/problems/kth-largest-element-in-an-array/     |   —    |   —    |   ✅   |  ✅   |   ✅    |           |
|  Easy  | 703. Kth Largest Element in a Stream      | https://leetcode.com/problems/kth-largest-element-in-a-stream/     |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 347. Top K Frequent Elements              | https://leetcode.com/problems/top-k-frequent-elements/             |   ✅    | 25.0%  |   —   |  —   |   ✅    |           |
| Medium | 451. Sort Characters By Frequency         | https://leetcode.com/problems/sort-characters-by-frequency/        |   —    |   —    |   —   |  —   |   —    |           |
|  Easy  | 1046. Last Stone Weight                   | https://leetcode.com/problems/last-stone-weight/                   |   —    |   —    |   —   |  —   |   —    |           |
|  Hard  | 502. IPO                                  | https://leetcode.com/problems/ipo/                                 |   —    |   —    |   ✅   |  —   |   —    |           |
|  Hard  | 295. Find Median from Data Stream         | https://leetcode.com/problems/find-median-from-data-stream/        |   ✅    | 37.5%  |   ✅   |  —   |   ✅    |           |
| Medium | 1962. Remove Stones to Minimize the Total | https://leetcode.com/problems/remove-stones-to-minimize-the-total/ |   —    |   —    |   —   |  —   |   —    |           |
|  Hard  | 23. Merge k Sorted Lists                  | https://leetcode.com/problems/merge-k-sorted-lists/                |   ✅    | 50.0%  |   ✅   |  —   |   ✅    |           |
| Medium | 373. Find K Pairs with Smallest Sums      | https://leetcode.com/problems/find-k-pairs-with-smallest-sums/     |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 2336. Smallest Number in Infinite Set     | https://leetcode.com/problems/smallest-number-in-infinite-set/     |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 2462. Total Cost to Hire K Workers        | https://leetcode.com/problems/total-cost-to-hire-k-workers/        |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 2542. Maximum Subsequence Score           | https://leetcode.com/problems/maximum-subsequence-score/           |   —    |   —    |   —   |  ✅   |   —    |           |

# 16. Graph General

| Level  | Name                                                | Link                                                                         | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:----------------------------------------------------|:-----------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 841. Keys and Rooms                                 | https://leetcode.com/problems/keys-and-rooms/                                |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 1971. Find if Path Exists in Graph                  | https://leetcode.com/problems/find-if-path-exists-in-graph/                  |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 133. Clone Graph                                    | https://leetcode.com/problems/clone-graph/                                   |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 1557. Minimum Number of Vertices to Reach All Nodes | https://leetcode.com/problems/minimum-number-of-vertices-to-reach-all-nodes/ |   —    |   —    |   —   |  —   |   —    |           |
|  Easy  | 1436. Destination City                              | https://leetcode.com/problems/destination-city/                              |   ✅    | 37.5%  |   —   |  —   |   —    |           |
| Medium | 130. Surrounded Regions                             | https://leetcode.com/problems/surrounded-regions/                            |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 399. Evaluate Division                              | https://leetcode.com/problems/evaluate-division/                             |   —    |   —    |   ✅   |  ✅   |   —    |           |

# 17. Graph DFS

| Level  | Name                                                         | Link                                                                                  | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:-------------------------------------------------------------|:--------------------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 547. Number of Provinces                                     | https://leetcode.com/problems/number-of-provinces/                                    |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 200. Number of Islands                                       | https://leetcode.com/problems/number-of-islands/                                      |   ✅    | 62.5%  |   ✅   |  —   |   ✅    |           |
| Medium | 1466. Reorder Routes to Make All Paths Lead to the City Zero | https://leetcode.com/problems/reorder-routes-to-make-all-paths-lead-to-the-city-zero/ |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 695. Max Area of Island                                      | https://leetcode.com/problems/max-area-of-island/                                     |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 2368. Reachable Nodes With Restrictions                      | https://leetcode.com/problems/reachable-nodes-with-restrictions/                      |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 542. 01 Matrix                                               | https://leetcode.com/problems/01-matrix/                                              |   —    |   —    |   —   |  —   |   —    |           |
|  Hard  | 332. Reconstruct Itinerary                                   | https://leetcode.com/problems/reconstruct-itinerary/                                  |   ✅    | 50.0%  |   —   |  —   |   —    |           |

# 18. Graph BFS

| Level  | Name                                        | Link                                                                 | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:--------------------------------------------|:---------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 1129. Shortest Path with Alternating Colors | https://leetcode.com/problems/shortest-path-with-alternating-colors/ |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 1926. Nearest Exit from Entrance in Maze    | https://leetcode.com/problems/nearest-exit-from-entrance-in-maze/    |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 1091. Shortest Path in Binary Matrix        | https://leetcode.com/problems/shortest-path-in-binary-matrix/        |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 752. Open the Lock                          | https://leetcode.com/problems/open-the-lock/                         |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 433. Minimum Genetic Mutation               | https://leetcode.com/problems/minimum-genetic-mutation/              |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 994. Rotting Oranges                        | https://leetcode.com/problems/rotting-oranges/                       |   ✅    | 25.0%  |   —   |  ✅   |   ✅    |           |
|  Hard  | 127. Word Ladder                            | https://leetcode.com/problems/word-ladder/                           |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 909. Snakes and Ladders                     | https://leetcode.com/problems/snakes-and-ladders/                    |   —    |   —    |   ✅   |  —   |   —    |           |

# 19. Topological Sort

| Level  | Name                                                | Link                                                                         | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:----------------------------------------------------|:-----------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 2115. Find All Possible Recipes from Given Supplies | https://leetcode.com/problems/find-all-possible-recipes-from-given-supplies/ |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 207. Course Schedule                                | https://leetcode.com/problems/course-schedule/                               |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 210. Course Schedule II                             | https://leetcode.com/problems/course-schedule-ii/                            |   —    |   —    |   ✅   |  —   |   —    |           |

# 20. Dijkstra

| Level  | Name                                 | Link                                                           | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:-------------------------------------|:---------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 743. Network Delay Time              | https://leetcode.com/problems/network-delay-time/              |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 1514. Path with Maximum Probability  | https://leetcode.com/problems/path-with-maximum-probability/   |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 787. Cheapest Flights Within K Stops | https://leetcode.com/problems/cheapest-flights-within-k-stops/ |   —    |   —    |   —   |  —   |   —    |           |

# 21. Backtracking

| Level  | Name                                      | Link                                                                 | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:------------------------------------------|:---------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 46. Permutations                          | https://leetcode.com/problems/permutations/                          |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 77. Combinations                          | https://leetcode.com/problems/combinations/                          |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 78. Subsets                               | https://leetcode.com/problems/subsets/                               |   —    |   —    |   —   |  —   |   ✅    | 2         |
| Medium | 22. Generate Parentheses                  | https://leetcode.com/problems/generate-parentheses/                  |   ✅    | 50.0%  |   ✅   |  —   |   ✅    |           |
| Medium | 216. Combination Sum III                  | https://leetcode.com/problems/combination-sum-iii/                   |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 17. Letter Combinations of a Phone Number | https://leetcode.com/problems/letter-combinations-of-a-phone-number/ |   ✅    | 37.5%  |   ✅   |  ✅   |   ✅    |           |
|  Hard  | 51. N-Queens                              | https://leetcode.com/problems/n-queens/                              |   —    |   —    |   —   |  —   |   ✅    |           |
|  Hard  | 489. Robot room cleaner                   | https://leetcode.com/problems/robot-room-cleaner/                    |   —    |   —    |   —   |  —   |   —    |           |
|  Easy  | 257. Binary Tree Paths                    | https://leetcode.com/problems/binary-tree-paths/                     |   —    |   —    |   —   |  —   |   —    | 2         |
| Medium | 784. Letter Case Permutation              | https://leetcode.com/problems/letter-case-permutation/               |   —    |   —    |   —   |  —   |   —    | 2         |
| Medium | 39. Combination Sum                       | https://leetcode.com/problems/combination-sum/                       |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 79. Word Search                           | https://leetcode.com/problems/word-search/                           |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 90. Subsets II                            | https://leetcode.com/problems/subsets-ii/                            |   —    |   —    |   —   |  —   |   —    |           |
|  Hard  | 52. N-Queens II                           | https://leetcode.com/problems/n-queens-ii/                           |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 131. Palindrome Partitioning              | https://leetcode.com/problems/palindrome-partitioning/               |   —    |   —    |   —   |  —   |   ✅    |           |

**Рекомендованный порядок изучения (от простого к сложному):**

1. **78. Subsets** — база: "решающее дерево" (брать элемент / не брать).
2. **77. Combinations** — то же самое, но с ограничением размера `k`.
3. **90. Subsets II** — подмножества с дубликатами: сортировка + пропуск повторов (
   `if i > start and nums[i] == nums[i-1]: continue`).
4. **39. Combination Sum** — комбинации на сумму, элемент можно брать повторно.
5. **46. Permutations** — важен порядок, нужен `visited`-массив.
6. **17. Letter Combinations of a Phone Number** — маппинг цифра → буквы, рекурсия по индексу строки.
7. **22. Generate Parentheses** — рекурсия с отсечением по условиям (`open < n`, `close < open`).
8. **79. Word Search** — DFS по матрице + откат visited-состояния (вершина паттерна).

Если уверенно решаете эти 8 — закрыто около 90% вопросов по Backtracking на собеседованиях.

# 22. Divide & Conquer

| Level  | Name                     | Link                                               | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:-------------------------|:---------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 148. Sort List           | https://leetcode.com/problems/sort-list/           |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 427. Construct Quad Tree | https://leetcode.com/problems/construct-quad-tree/ |   —    |   —    |   ✅   |  —   |   —    |           |

# 23. Dynamic Programming

| Level  | Name                                                      | Link                                                                                | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:----------------------------------------------------------|:------------------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
|  Easy  | 509. Fibonacci Number                                     | https://leetcode.com/problems/fibonacci-number/                                     |   —    |   —    |   —   |  —   |   —    |           |
|  Easy  | 70. Climbing Stairs                                       | https://leetcode.com/problems/climbing-stairs/                                      |   —    |   —    |   ✅   |  —   |   ✅    |           |
|  Easy  | 746. Min Cost Climbing Stairs                             | https://leetcode.com/problems/min-cost-climbing-stairs/                             |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 322. Coin Change                                          | https://leetcode.com/problems/coin-change/                                          |   ✅    | 25.0%  |   ✅   |  —   |   ✅    |           |
| Medium | 198. House Robber                                         | https://leetcode.com/problems/house-robber/                                         |   —    |   —    |   ✅   |  ✅   |   ✅    |           |
| Medium | 91. Decode Ways                                           | https://leetcode.com/problems/decode-ways/                                          |   —    |   —    |   —   |  —   |   —    |           |
| Medium | 62. Unique Paths                                          | https://leetcode.com/problems/unique-paths/                                         |   —    |   —    |   —   |  ✅   |   ✅    |           |
| Medium | 64. Minimum Path Sum                                      | https://leetcode.com/problems/minimum-path-sum/                                     |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 72. Edit Distance                                         | https://leetcode.com/problems/edit-distance/                                        |   —    |   —    |   ✅   |  ✅   |   ✅    |           |
| Medium | 5. Longest Palindromic Substring                          | https://leetcode.com/problems/longest-palindromic-substring/                        |   ✅    | 75.0%  |   ✅   |  —   |   ✅    |           |
| Medium | 161. One Edit Distance                                    | https://leetcode.com/problems/one-edit-distance/                                    |   ✅    | 75.0%  |   —   |  —   |   —    |           |
| Medium | 53. Maximum Subarray                                      | https://leetcode.com/problems/maximum-subarray/                                     |   ✅    | 50.0%  |   ✅   |  —   |   ✅    |           |
| Medium | 279. Perfect Squares                                      | https://leetcode.com/problems/perfect-squares/                                      |   ✅    | 50.0%  |   —   |  —   |   ✅    |           |
|  Easy  | 121. Best Time to Buy and Sell Stock                      | https://leetcode.com/problems/best-time-to-buy-and-sell-stock/                      |   ✅    | 37.5%  |   ✅   |  —   |   ✅    |           |
| Medium | 300. Longest Increasing Subsequence                       | https://leetcode.com/problems/longest-increasing-subsequence/                       |   ✅    | 37.5%  |   ✅   |  —   |   ✅    |           |
|  Hard  | 32. Longest Valid Parentheses                             | https://leetcode.com/problems/longest-valid-parentheses/                            |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | 63. Unique Paths II                                       | https://leetcode.com/problems/unique-paths-ii/                                      |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 97. Interleaving String                                   | https://leetcode.com/problems/interleaving-string/                                  |   —    |   —    |   ✅   |  —   |   —    |           |
|  Easy  | 118. Pascal's Triangle                                    | https://leetcode.com/problems/pascals-triangle/                                     |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | 120. Triangle                                             | https://leetcode.com/problems/triangle/                                             |   —    |   —    |   ✅   |  —   |   —    |           |
|  Hard  | 123. Best Time to Buy and Sell Stock III                  | https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iii/                  |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 139. Word Break                                           | https://leetcode.com/problems/word-break/                                           |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 152. Maximum Product Subarray                             | https://leetcode.com/problems/maximum-product-subarray/                             |   —    |   —    |   —   |  —   |   ✅    |           |
|  Hard  | 188. Best Time to Buy and Sell Stock IV                   | https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iv/                   |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 221. Maximal Square                                       | https://leetcode.com/problems/maximal-square/                                       |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 416. Partition Equal Subset Sum                           | https://leetcode.com/problems/partition-equal-subset-sum/                           |   —    |   —    |   —   |  —   |   ✅    |           |
| Medium | 714. Best Time to Buy and Sell Stock with Transaction Fee | https://leetcode.com/problems/best-time-to-buy-and-sell-stock-with-transaction-fee/ |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 790. Domino and Tromino Tiling                            | https://leetcode.com/problems/domino-and-tromino-tiling/                            |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 918. Maximum Sum Circular Subarray                        | https://leetcode.com/problems/maximum-sum-circular-subarray/                        |   —    |   —    |   ✅   |  —   |   —    |           |
|  Easy  | 1137. N-th Tribonacci Number                              | https://leetcode.com/problems/n-th-tribonacci-number/                               |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 1143. Longest Common Subsequence                          | https://leetcode.com/problems/longest-common-subsequence/                           |   —    |   —    |   —   |  ✅   |   ✅    |           |

# 24. Greedy

| Level  | Name                                     | Link                                                               | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:-----------------------------------------|:-------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 849. Maximize Distance to Closest Person | https://leetcode.com/problems/maximize-distance-to-closest-person/ |   ✅    | 87.5%  |   —   |  —   |   —    |           |
| Medium | 55. Jump Game                            | https://leetcode.com/problems/jump-game/                           |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 45. Jump Game II                         | https://leetcode.com/problems/jump-game-ii/                        |   —    |   —    |   ✅   |  —   |   ✅    |           |
| Medium | 134. Gas Station                         | https://leetcode.com/problems/gas-station/                         |   —    |   —    |   ✅   |  —   |   —    |           |
| Medium | 435. Non-overlapping Intervals           | https://leetcode.com/problems/non-overlapping-intervals/           |   —    |   —    |   —   |  ✅   |   —    |           |

# 25. Bit Manipulation

| Level  | Name                         | Link                                                  | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:-----------------------------|:------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 1386. Cinema Seat Allocation | https://leetcode.com/problems/cinema-seat-allocation/ |   ✅    | 25.0%  |   —   |  —   |   —    |           |
|  Easy  | 136. Single Number           | https://leetcode.com/problems/single-number/          |   —    |   —    |   ✅   |  ✅   |   ✅    |           |
|  Easy  | 338. Counting Bits           | https://leetcode.com/problems/counting-bits/          |   —    |   —    |   —   |  ✅   |   —    |           |
| Medium | 78. Subsets                  | https://leetcode.com/problems/subsets/                |   —    |   —    |   —   |  —   |   ✅    |           |

# 26. Design / OOP

| Level  | Name                                                                              | Link                                                       | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:----------------------------------------------------------------------------------|:-----------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 380. Insert Delete GetRandom O(1)                                                 | https://leetcode.com/problems/insert-delete-getrandom-o1/  |   ✅    | 62.5%  |   ✅   |  —   |   —    |           |
| Medium | 281. Zigzag Iterator                                                              | https://leetcode.com/problems/zigzag-iterator/             |   ✅    | 25.0%  |   —   |  —   |   —    |           |
| Medium | 362. Design Hit Counter                                                           | https://leetcode.com/problems/design-hit-counter/          |   ✅    | 50.0%  |   —   |  —   |   —    |           |
|  Easy  | 1656. Design an Ordered Stream                                                    | https://leetcode.com/problems/design-an-ordered-stream/    |   ✅    | 37.5%  |   —   |  —   |   —    |           |
| Medium | 2241. Design an ATM Machine                                                       | https://leetcode.com/problems/design-an-atm-machine/       |   ✅    | 62.5%  |   —   |  —   |   —    |           |
| Medium | 155. Min Stack                                                                    | https://leetcode.com/problems/min-stack/                   |   ✅    | 62.5%  |   ✅   |  —   |   ✅    |           |
| Medium | 146. LRU Cache                                                                    | https://leetcode.com/problems/lru-cache/                   |   ✅    | 50.0%  |   ✅   |  —   |   ✅    |           |
|  Easy  | 2629. Function Composition *(JS-задача, низкая релевантность для бэкенда)*        | https://leetcode.com/problems/function-composition/        |   ✅    | 37.5%  |   —   |  —   |   —    |           |
|  Easy  | 2665. Counter II *(JS-задача, низкая релевантность для бэкенда)*                  | https://leetcode.com/problems/counter-ii/                  |   ✅    | 25.0%  |   —   |  —   |   —    |           |
|  Easy  | 2666. Allow One Function Call *(JS-задача, низкая релевантность для бэкенда)*     | https://leetcode.com/problems/allow-one-function-call/     |   ✅    | 37.5%  |   —   |  —   |   —    |           |
|  Easy  | 2667. Create Hello World Function *(JS-задача, низкая релевантность для бэкенда)* | https://leetcode.com/problems/create-hello-world-function/ |   ✅    | 25.0%  |   —   |  —   |   —    |           |

# 27. Math / Simulation

| Level  | Name                                  | Link                                                        | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:------:|:--------------------------------------|:------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Medium | 7. Reverse Integer                    | https://leetcode.com/problems/reverse-integer/              |   ✅    | 25.0%  |   —   |  —   |   —    |           |
|  Easy  | 9. Palindrome Number                  | https://leetcode.com/problems/palindrome-number/            |   ✅    | 37.5%  |   ✅   |  —   |   —    |           |
|  Easy  | 415. Add Strings                      | https://leetcode.com/problems/add-strings/                  |   ✅    | 37.5%  |   —   |  —   |   —    |           |
| Medium | 470. Implement Rand10() Using Rand7() | https://leetcode.com/problems/implement-rand10-using-rand7/ |   ✅    | 25.0%  |   —   |  —   |   —    |           |

# 28. SQL

| Level | Name                                            | Link                                                                      | Yandex | Freq % | TP150 | LC75 | Top100 | Retention |
|:-----:|:------------------------------------------------|:--------------------------------------------------------------------------|:------:|:------:|:-----:|:----:|:------:|:----------|
| Easy  | 181. Employees Earning More Than Their Managers | https://leetcode.com/problems/employees-earning-more-than-their-managers/ |   ✅    | 25.0%  |   —   |  —   |   —    |           |

## Методология и источники

- Список задач и структура тем — личная подборка, ориентированная на подготовку к алгоритмическим собеседованиям (
  FAANG-style + Яндекс).
- **Yandex / Freq %** сверены по датасету [
  `yandex/all.csv`](https://github.com/snehasishroy/leetcode-companywise-interview-questions/blob/master/yandex/all.csv)
  из [snehasishroy/leetcode-companywise-interview-questions](https://github.com/snehasishroy/leetcode-companywise-interview-questions) (
  снимок на 2026-08-21, 130 задач).
- **TP150 / LC75 / Top100** сверены напрямую по официальным LeetCode study plans через их публичный GraphQL API (снимок
  на 2026-08-26): [Top Interview 150](https://leetcode.com/studyplan/top-interview-150/) (150 задач, 23
  темы), [LeetCode 75](https://leetcode.com/studyplan/leetcode-75/) (75 задач, 22
  темы), [Top 100 Liked Questions](https://leetcode.com/studyplan/top-100-liked/) (100 задач, 15 тем).
- Темы **Greedy / Bit Manipulation / Monotonic Stack / Design-OOP / Divide & Conquer** собраны заново; часть задач
  добавлена только как база для тренировки паттерна (без меток, `—`), часть — реально встречается в одном из
  источников (✅).
- Порядок тем — единая линейная последовательность (без веток) от простого к сложному с учётом зависимостей между
  паттернами; обоснование каждого шага — в списке выше.
- 4 задачи в разделе **Design / OOP** (Function Composition, Counter II, Allow One Function Call, Create Hello World
  Function) помечены как низкорелевантные — это JS-специфичные задачи на замыкания/функциональщину из трека LeetCode "30
  Days of JS", вряд ли актуальны для Python-бэкенд-собеседования, но тегированы Yandex в источнике — оставлены для
  полноты.
- Задача, которая по своей природе решается двумя разными стандартными способами (например Trapping Rain Water — two
  pointers и monotonic stack), намеренно оставлена в обеих подходящих темах, а не только в "основной".
- Retention заполняется вручную по шкале в начале файла после решения каждой задачи.
