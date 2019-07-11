# Optional

### What is Optional?

每一個變數，就很像是一個可以裝東西的盒子；我們必須清楚的告訴電腦，這個盒子即將用來儲存什麼樣的資料（`Int`）。

```swift
var number: Int = 10
```

一但你宣告了 `Int`, 代表這個變數裡面只能放 `整數`，**而且一定要有值**。

> 在 Swift 裡面，有一個特別的值，**用來描述變數裡空無一物的狀態**，稱之為 `nil`。

如果一個變數，裡面可能有值，也有可能沒有值，Swift 特別為了這個狀態，創造了一個名詞來描述，就稱之為 `Optional`，表示方式為在變數型別後面加上 `?`


```swift
var number: Int = 10  // number 的型別為 Int, 也就是 number 這個變數，裡面一定會有值

var targetNumber: Int? = 20 // targetNumber 的型別為 Int?, 稱之為 Optional Int, 也就是 targetNumber 這個變數，裡面不一定會有值

number = nil //Fail, 當一個變數不是 optional type, 就不可以放 nil 進去，也就是裡面不可以是空值

targetNumber = nil //Pass, Optional Int 可以接受 nil, 因為是 Optional type
```

任何型別，只要在後面加上 `?`，就是 **Optional** 的意思，可以接受 `nil`

```swift
var name: String = "Luke" //Data type String. Don't accept nil.

var nickName: String? = nil //Data type Optional String. Accept nil.

var price: Double = 123.4 //Data type Double. Don't accept nil.

var specialPrice: Double? = nil //Data type Optional Double. Accept nil.
```

### How to deal with optional?
當我們遇到了一個 `Optional Type` 的變數，Swift 提供了兩個方法讓我們可以確認，檢查裡面到底有沒有值

**1. guard let 語法**. 

讓我們來看個範例：

```swift
var specialPrice: Int? = 10 

guard let price = specialPrice else {

    print("There is no value in sepcialPrice variable.")

    return 
}

print("There is \(price) in specialPrice variable.")
```

1. 當 `specialPrice` 裡面有值，這個值就會被拿出來，儲存到新的變數 `price` 裡面
2. 如果 `specialPrice` 裡面沒有值，是 `nil` 的時候，就會執行 `else` 後面的 **大括號內的程式碼，且大括號後面的程式碼都不會執行**。

上述的程式碼，就會在 console 印出：
```
There is 10 in specialPrice variable.
```

註：Playground 不太適合練習 `guard let` 語法，請開 Xcode project 練習比較好，將這些程式碼寫在 `viewDidLoad` 裡面即可。

---

如果把 `specialPrice` 改成 `nil`，如下：

```swift
var specialPrice: Int? = nil 

guard let price = specialPrice else {

    print("There is no value in sepcialPrice variable.")

    return 
}

print("There is \(price) in specialPrice variable.")
```

就會在 console 印出：

```
There is no value in sepcialPrice variable.
```

要注意的是，`print("There is \(price) in specialPrice variable.")` 並沒有被執行。

**2. if-let**

讓我們以相同的應用來試試看：

```swift

print("Before if-let statement.")

var specialPrice: Int? = 10 

if let price = specialPrice {

    print("There is \(price) in specialPrice variable.")

} else {

    print("There is no value in sepcialPrice variable.")
}

print("After if-let statement.")

//print(price) will cause error. Because variable is not visible.(scope)

```

Console will output:
```
Before if-let statement.
There is 10 in specialPrice variable.
After if-let statement.
```

1. 當 `specialPrice` 裡面有值，這個值就會被拿出來，儲存到新的變數 `price` 裡面，但只能在 `if statement` 裡面使用，離開了 if statement 就沒有這個 constant 可以用了。
2. 如果 `specialPrice` 裡面沒有值，是 `nil` 的時候，就會執行 `else` 裡面的程式碼。
3. 跟 `guard let` 不一樣的是，無論 specialPrice 裡面有沒有值，`print("After if-let statement.")` 都會被執行。`guard let` 如果失敗，執行完 else 內的程式碼就結束了，不會再繼續下去。

如果把 `specialPrice` 改成 `nil`，則 console will output：

```
Before if-let statement.
There is no value in sepcialPrice variable.
After if-let statement.
```

### Handle mutiple optional value
你也可以一次處理多個 `optional type` 的變數：

#### guard let

```swift
var userInput: String? = "200"

var nickName: String? = "Luke"

guard let input = userInput,
      let name = nickName else {

    print("Find optional value.")

    return 
}

print("\(name) input \(input)")

```

Console will output: 
```
Luke input 200
```

`userInput` 與 `nickName` 都有值，才會 `print("\(name) input \(input)")`；否則就會進到 `else` 裡面，`print("Find optional value.")`。

註：Playground 不太適合練習 `guard let` 語法，請開 Xcode project 練習比較好，將這些程式碼寫在 `viewDidLoad` 裡面即可。

#### if let

```swift
var userInput: String? = "200"

var nickName: String? = "Luke"

if let name = nickName,
   let input = userInput {

    print("\(name) input \(input)")

} else {

    print("Find optional value.")
}

print("After if-let statement.")

```

Console will output: 
```
Luke input 200
After if-let statement.
```

### Force Unwrapped

有時候我們想省略複雜的檢查手續（無論是 `guard let` 或 `if let`），我可以可以透過 Force Unwrapped 來達成這個目的。

```swift
var nickName: String? = "Luke"

let name = nickName!

//name data type will be String, not String?
```

在 `Optional type` 的變數後面加上 `!`，就是 Force Unwrapped 的語法，它的功能是：

1. 我們告訴電腦，雖然這個變數的型別是 optional，但我知道裡面現在有值，請幫我把值拿出來。
2. 如果 `!` 遇上 `nil`，app 就會 crash。


```swift
var specialPrice: Double? = nil

specialPrice!   //This will cause crash.
```

### Nil Coalescing Operator

還有另外一個 Operator 可以幫助我們處理 `nil`，是 `??` operator.

```swift
var nickName: String? = nil

let name = nickName ?? "No name."

print(name)
```

Console will output:
```
No name.
```

如果 `nickName` 有值，則這個值會被存進 `name` 裡面；如果 `nickName` 沒有值，則 "No name" 這個 String 會被存進 `name` 這個變數裡面。

# 練習

1. 
有一個 String "123"，我們嘗試將它轉成 Int data type，請利用 `guard let` 與 `if let` 檢查這個轉型是否成功
```swift
var stringToConvert = "123"

var number = Int(stringToConvert)

//Verify number is nil or not

```

2. 如果 `numberOfVolunteer` 不是 nil，請將人數 print 出來；如果是 nil，請 print 沒有自願者。（請分別用 if let 與 guard let 練習）

3. 有一個訂票網站，透過 `numberOfTickets` 來記錄使用者訂購的票卷數目，如果 numberOfTickets 是 nil，請給他一個預設值 1。

    Hint: 請使用 `??` Operator 完成這一題

4. 請問下列程式碼編譯時會發生什麼事？

```swift
var friends: Int? = nil

print(friends!)
```