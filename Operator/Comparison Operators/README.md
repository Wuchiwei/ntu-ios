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

# = 與 == 的差別

在程式的世界， “=” 是指定的意思，而 ”==” 是比較是否相等的意思，這跟我們平常的習慣不一樣。

```swift
x = 3     //把 3 這個值指定到 x 這個變數裡面

x == 3    //判斷 x 變數所儲存的值，跟 3 是否相同
```

# Logic AND and OR

### Logic AND: &&
當我們要判斷多重條件，舉例來說：男性 180 cm 以上，才可以參加男子籃球隊。此時參加條件為：

1. 必須是男性
2. 身高要 180 cm 以上

如果我們把以上的內容，簡單的 if-statement 來實現：

```swift
if (必須是男性) 而且 (身高 180 以上) {

    print("可以加入男子籃球隊！")

}
```

這個 `而且` 的功能，就要靠 Logic AND Operator **&&** 來完成。

```
let c = a && b
```

**Rule:**
1. a 與 b 必須都是 Boolean Data Type.
2. 運算完的結果 c 也會是 Boolean Type.
3. 如果 a, b 皆為 true, 則 c 為 true. 如果 a, b 其中一個為 false，則 c 為 false.

請看一下程式碼：

```swift
// 如果衣服價格維持在 700~1000 之間，我們的利潤就會上升兩成，否成盈利就不會成長

var clothPrice = 800

if (clothPrice >= 700) && (clothPrice <= 1000) {

    print("利潤就會上升兩成")

} else {

    print("盈利就不會成長")

}
```

此時 Console 會出現 

```
利潤就會上升兩成
```

### Logic OR: ||

另外一個可以拿來判斷多重條件的就是 Logic OR || : 

```
let c = a || b
```

**Rule:**
1. a 與 b 必須都是 Boolean Data Type.
2. 運算完的結果 c 也會是 Boolean Type.
3. 如果 a, b 皆為 false, 則 c 為 false. 如果 a, b 其中一個為 true，則 c 為 true.

請看一下程式碼：

```swift
// 只要是紅色或藍色，都可以跟我們的背景順利的搭配

var color = "Red"

if (color == "Red") || (color == "Blue") {

    print("可以與背景順利搭配")

} else {

    print("無法搭配")

}
```

此時 Console 會出現 

```
可以與背景順利搭配
```

### Logic NOT: !


```
let a: Bool = true

let b = !a //b will be false
```

# 練習

1. 請寫下 Console 會出現哪一段文字

```swift
var isRaining = true

if !isRaining {

    print("沒雨了，我要出門運動！")

} else {

    print("下雨了，我只好在家耍廢！")

}
```

2. 請寫下 Console 會出現哪一段文字 

```swift
var name = "Luke"

var money = 1000

if (name == "Luke") && (money > 2000) {

    print("你可以買雙鞋！")

} else {

    print("抱歉，你不可以買雙鞋！")
}

```

3. 請寫下 Console 會出現哪一段文字 

```swift
var age = 10

if (age < 0) || (age > 123) {

    print("年齡超出合理範圍")

} else {

    print("合理的年齡")
}
```
