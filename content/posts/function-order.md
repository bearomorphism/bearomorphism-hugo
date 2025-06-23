---
date: 2025-06-22T23:46:18+08:00
title: Function Order 是什麼？可以吃嗎？
math: true
---

前陣子在臉書討論區看到 Kuanling Huang 大大寫了[一篇文章](https://hackmd.io/@caasih/function-order)在講 "function order"。

我一開始懷疑這位大大在亂寫（結論是這位大大沒寫錯），於是就稍微查了一些資料研究了一下所謂 function order 到底是什麼。

相關的臉書討論區討論串在[這裡](https://www.facebook.com/groups/521085554595481/?multi_permalinks=9815821941788416&hoisted_section_header_type=recently_seen)。

後來資料找一找就找到 Type Theory 去了。

我除了讀書會時聽過同事講過幾次 lambda calculus 以外完全沒有碰過 Type Theory 相關的東西，我也不是專家，只是大學時多拿了一個數學學位而已。

如果下面有講錯歡迎留言指正，請各位多加包涵。

---

為了保持我這篇文章的完整性，我把 function order 的定義寫在這裡：

We denote "the order of a type $T$" as $ord(T)$.
1. For any primitive type $R$, $ord(R) := 0$.
2. For any product type $(A_1, ..., A_n)$, $ord((A_1, ..., A_n)) := \max(ord(A_1), ..., ord(A_n))$.
3. For any types $A$, $B$, $ord(A \to B) := \max(ord(A) + 1, ord(B))$.

我其實不是很確定有沒有更通用的用語，每篇文獻或課本會用不太一樣的詞，總之名詞定義大家先看得懂就好。

什麼是 primitive type 呢？例如 `int`, `boolean`, `char` 這些簡單的東西，都可以算是 primitive type。我其實不是很確定 `void` 或 `NoneType` 這種 [initial and terminal objects](https://en.wikipedia.org/wiki/Initial_and_terminal_objects) 到底算不算 primitive type，感覺如果算進 primitive type 的話，上面的 function order 定義會有一些問題。另外維基百科也有 [primitive type](https://en.wikipedia.org/wiki/Primitive_data_type)，一併附在這邊給大家參考。

什麼是 product type 呢？很不精確地說，可以把 product type 想成 tuple

- 比較熟 C++ 的人可以想想 `std::tuple<int, bool, char>` 之類的型別
- 比較熟 Python 的朋友們可以想想 `Tuple[int, bool, str]`
- 比較熟 TypeScript 就想想 `[int, bool, string]`

接著來講講同構，很不精確的來說，長得差不多一樣、可以互相換來換去的型別就是同構的

- `std::pair<int, char>` 跟 `std::pair<char, int>` 同構
- `std::pair<int, pair<int, int>>` 跟 `std::pair<std::pair<int, int>, int>` 跟 `std::tuple<int, int, int>` 同構
- $(A, B) \to C$ 跟 $A \to (B \to C)$ 同構 (currying)

而同構的 type 的 order 理想上要一樣，我們可以簡單檢查上面 function order 在同構的型別上算出來是一樣的。

如果讀到這邊還是不懂 product 或同構定義也沒差，請容我草草帶過，細講大概會扯到抽象代數或範疇論。

這邊的 takeaway 就是

- 最簡單的那些 type 的 order 是 0
- 每多抽象一層（這個 type 作為某個 function 的參數型別）的話，order 就會加一。

---

**Quiz**

1. What is `ord(int)`?
2. What is `ord(int -> int)`?
3. What is `ord(type(array.map))`, where `array.map` is the javascript function?
4. What is `ord(type(filter)) = ord((Any -> boolean) -> List)`, where `filter` is the built-in python function?

---

讀到這邊，你會算 function order 了嗎？

其實我覺得不會算也沒差啦，只是一開始提到的文章內文給人一種「身為一個工程師卻不會算 function order 很糟糕」的感覺。

比起會不會算 function order，我認為能了解每個變數或每個參數的型別以及其背後的意義是比較重要的。

尤其是在了解一些 functional programming pattern 時，會看到諸如 `(T, T) -> T` 或 `T -> boolean` 等等型別，「不要被這些型別嚇得半死」我覺得就已經很好了。

當然，當我們拿到一個 type 後，我們可以去算這個 type 的 order，但當我們只看 order 時就會失去太多原本的資訊，所以我覺得去算 order 其實沒什麼必要。

各位工程師應該都有寫過或聽過 `std::sort`, `array.map`, `array.reduce` 或 `filter` 等等 function。

你們在使用這些 function 前會去算他們的 order 嗎？不會吧？

也難怪網路上很難直接查到 type order 的資料，實務上就很少會用到，甚至 type theory 相關的文獻也不會在 type order 上著墨太多。

---

其實找資料花了我一段時間，因為直接查 function order 並不會查到上面的定義。如果大家直接查 function order 或 order of a function 的話，可能會查到

- Complexity theory
  - 例如一個 function $f(n) = n(n + 1) / 2 = O(n^2)$，我們在這個上下文會說 $f$ 的 order 是 2
- Group theory 意義下的 order，也就是一個 element 自乘幾次會變成 1
  - 例如定義 $f(z) = iz$，因為 $f^4(z) = f(f(f(f(z)))) = i^4 z = z$ 且 4 是最小的正整數 $n$ 使得 $f^n(z) = z$，我們在 group theory 的上下文會說 $f$ 的 order 是 4

最後查一查就查到 type theory 了，裡面才有最接近一開始提到的文章講的 type order 的定義。
