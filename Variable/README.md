# 變數與常數

寫程式一開始要學會的事情，就是要學會怎麼把一筆資料，告訴電腦。舉例來說，如果我們希望完成類似計算機的功能，那我們需要把使用者選的數字， **儲存在電腦裡面** ，後續才有辦法做計算。

這個把資料餵給電腦的動作，我們稱之為 **將資料儲存在變數(常數)裡**

下列的語法是，宣告 (declare) 一個變數或常數，並將資料儲存在裡面：

```swift
var length = 10

let gender = "男生"
```

### 變數與常數
其中 `var` 代表 `length` 裡面儲存的資料，是可以做修改的，這種特性又稱之為變數 **variable**。而 `let` 代表 `gender` 裡面儲存的資料，是不可以修改的，這種特性又稱之為常數 **constant**。

```swift
var length = 10

length = 100 // Pass

let gender = "男生"

gender = "女生" //Error, 你不可以這樣做
```

### 命名規則

在 Swift 裡面，我們使用 **駝峰式 Camel Case** 的命名方式：我們使用完整的英文單字來表達這個變數所儲存資料的用意，必要時候會用多個英文單字。當我們使用多個英文單字，則 `第一個單字小寫，第二個以後的單字開頭大寫，其餘小寫`。

```swift
var weight = 100 //只有一個單字就全小寫

var numberOfStudents = 31 // Of, Students 開頭大寫，其餘小寫

var numberofstudents = 31 // 不建議這樣寫，雖然不會有 Error 發生，但會增加閱讀難度。
```

### 基本運算子

一般的加減乘除運算子，在 Swift 裡面都有支援，功能也都相同

```swift

let sum = 10 + 20 // 此為加法，sum 為 30

let diff = 100 - 60 // 此為減法，sum 為40

let result = 12 * 30 // 此為乘法，result 為 360

let payment = 1200 / 3 // 此為除法，result 為 400

```

另外有一個比較特別的運算子，英文叫 `Remainder Operator`，符號為 **%**，專門用來算餘數的。

```swift
9 % 4 // 運算結果為 1
```

### Print
當我們寫程式的時候，很常需要確認程式是不是正確，這個時候就會利用到 print 這個語法，他可以幫我們把變數內容顯示在畫面下方的 console 中，方便我們觀察程式碼的運作。

```swift
print("Hello, Swift")

let name = "Luke"

print(name)

var number = 10

print(number)
```

### 練習

1. 請宣告兩個變數 a, b，分別儲存 10 與 20，接著計算這兩個數的平均，並將之儲存在第三個變數 result 中。

2. 請利用 `secondInMinute` 這個變數，算出一天總共有幾秒，並儲存在 `secondInDay` 這個變數中

```swift
var secondInMinite = 60
```

3. 請利用下列兩個變數，在 Console 中輸出 "Hello World" 的結果

```swift
var firstWord = "Hello"

var secondWord = "World"
```

4. 請利用下列兩個變數，在 Console 中輸出 "Welcome to the new world!" 的結果

```swift
var firstWord = "Welcome to the"

var secondWord = "new world!"
```

5. 一打鉛筆有 12 支，請問 5 打有幾隻，請將計算結果儲存在 `result` 變數中

```swift
let numberOfPencil = 12
```

6. 有 x, y 兩個數，兩者相加為 10, 兩者相減為 2，請求出 x, y

```swift
let sum = 10 // x + y

let diff = 2 // x - y
```

7. 我們一群人去吃飯，總共有 43 個，但一桌只能坐 10 個人，請問我們總共需要幾桌，沒坐滿的那一桌，坐了幾個人