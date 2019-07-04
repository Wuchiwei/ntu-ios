# Data Type

在 Swift 裡面，有幾個原生的資料型態 primitive data type，他是用來代表一些已經存在於人類世界的資料型態。分別是 `Int`, `Double`, `Float`, `Boolean`, `String`, 以及一個比較特殊的名詞 `Optional`。

* Int 用來代表現實世界中的整數，泛指 0, 1, 2, 3 與 -1, -2, -3 這一類型的數值。
* Double 用來代表現實世界中的實數，泛指 1.2, 3.141, -1.5 等，但要注意的是，`整數也是實數的一部分，但實數不一定是整數`。
* Float 與 Double 用途一樣，只是 Float 能夠容納的範圍比較小，精準度比較低。
* Boolean 用來代表現實生活中的真假狀況，他只有兩個數值的可能，`true` 與 `false`。再擴大一點講，現實生活中的任何二分情況，都可以用 Boolean 來代表，比如說：有下雨 VS 沒下雨，正面 VS 反面，要吃東西 VS 不吃東西，etc.
* String 代表現實生活中的字串，但在 Swift 中，字串前後會以雙上引號 `"` 做為標示。

Example: 請判斷下列資料是屬於哪種資料型別

```Swift

10 // Int, Double, Float

false

20.5

"This is an apple."

true

50

```

# 再談變數宣告

讓我們再回顧一下先前的變數宣告:

```swift
var number = 10
```

上列的變數宣告方法，其實省略了一些東西，完整的寫法如下：

```swift
var number: Int = 10
```

讓我們一個部分一個部分的說明：

* `var` : 宣告一個 variable 的標示
* `number` : 變數名稱 Variable name
* `: Int` : 變數名稱後面先接一個冒號 `:`，再來接了一個 `Int`，這個 Int 的含義是 number 這個變數，所以裝載的資料型別是 Int

讓我們再來看看另外一個例子：

```swift
var name: String = "Luke" //pass

var age: Int = "Luke" //Error
```

我們宣告了 `name` 所裝載的資料型別為 **String**, 後續等號右邊的資料 "Luke" 也是 String，所以這一段程式碼沒有問題。但 `age` 我們宣告為 **Int**, 等號右邊卻還是給了 String "Luke"，這樣左右兩邊的狀態不一樣，Xcode 就會告訴你，這是不被允許的狀態。

### Type Inference

```swift
var number = 10

let name: String = "Luke"
```

上列兩個都是合法的變數宣告方法，
* `number` 沒有明確標明變數型別。
* `name` 有明確標明 `String` 這個變數型別。

當我們沒有明確註明變數型別的時候，Xcode 會利用等號右邊的數值，幫我們對這個變數加上型別，以 `number`
為例，現在他的 Data Type 就是 `Int`。

讓我們多看幾個例子：

```swift
var isRaining = false // isRaining 的 Data Type 為 Bool

var numberOfStars = 10000 // numberOfStars 的 Data Type 為 Integer

var speed = 10.2 // speed 的 Data Type 為 Double

var slogan = "That's make America great again!!" // slogan 的 Data Type 為 String 
```

這種沒有特別標出型別，讓 Xcode 根據資料幫我們覺得型別的狀態，稱之為 **Type Inference**。

```swift
var isOver = false

isOver = "Yes" //Error, 因為 isOver 是 Bool Data Type，不可以放 String 進去

isOver = true //Pass
```

＃練習

1. 請寫出下列變數的型別 ex: `let a = 10` -> `let a: Int = 10`

```swift
var isOpen = false 

var numberOfPeople = 10000

var oilPrice = 28.2

var artileTitle = "花蓮5天4夜輕旅行"
```

2. 請判斷下列程式碼是否能夠被執行

```swift
var price = 2600

price = 3000
```

```swift
var length = 2.6

length = 3000
```

```swift
var length = 2.6

length = "2.6"
```

```swift
var message = "1200"

message = 123
```