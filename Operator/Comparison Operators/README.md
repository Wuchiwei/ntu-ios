# Comparison Operators

跟現實生活中比大小的大於小於一樣，Swift 也有提供比大小的方法

* 等於 == (a == b)
* 不等於 (a != b)
* 大於 > (a > b)
* 小於 < (a < b)
* 大於等於 >= (a >= b)
* 小於等於 <= (a <= b)

1. 以上的運算子，在比較完之後，**都會產出一個 Boolean 的結果**
2. 只能比較相同型別的資料。

Example:

```swift

let a = 10 > 5 //a 為 true

let b = 10 < 5 //b 為 false

10 > "10" //Error, Int 與 String 不能比較

let c = 10 == 5 //c 為 false

let d = 10 != 5 //d 為 true

```