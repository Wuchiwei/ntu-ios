# If Statement

### Single if statement
日常生活中我們很常根據條件，做出判斷。比如說：

* 如果下雨，我就不出門。
* 假設 Peter 要出席，我就出席，否則我就不去了。
* 在進行一場球賽的時候，硬幣骰到正面，我先進攻; 反面，你先進攻。

這樣子的邏輯要怎麼在 Swift 中實現了，就要靠 `if-statement`

讓我們來看一下 Swift 的 if 語法，

<img src="https://github.com/Wuchiwei/ntu-ios/blob/master/ControlFlow/if-statement/images/if.png" alt="image" width="200"/>

* Condition: **只能放 Boolean 的值** ，也就是 `true` 或 `false`。

* Statements: 可以寫任何的 code， **但這一段 code 只有在上述的 Condition 為 true 的時候，才會被執行** 。

請看以下的例子：

```swift
var isRaining: Bool = true

print("-------------------")
print("Before if statement")

if isRaining {

    print("I don't want to go outside.")
}

print("-------------------")
print("After if statement")
```

這段程式碼執行的話，我們會在 Console 看到：

```
-------------------
Before if statement
I don't want to go outside.
-------------------
After if statement
```

如果我們把 `var isRaining: Bool = true` 改成 `var isRaining: Bool = false`

console 就會看到：

```
-------------------
Before if statement
-------------------
After if statement
```

讓我們再看另外一個例子：

```swift
var number = 100

//This will cause error.
if number {

    print("This is 100")
}
```

Xcode 會告訴你有錯誤，因為 if 後面的 statement 只能接 `Boolean`，上面的 number 是 `Int`，不能放在 if statement 後面。

---

### if-else statement
讓我們再來看另外一個現實生活中的情境：

* 假設 Peter 要出席，我就出席，否則我就不去了。

這種根據一個條件，有`兩種`不一樣的事情要做的狀況，就要利用到 `if-else` 語法：

<img src="https://github.com/Wuchiwei/ntu-ios/blob/master/ControlFlow/if-statement/images/if-else.png" alt="image" width="500"/>

```swift
var isPeterGoing = true

if isPeterGoing {

    print("I will go, too.")

} else {

    print("I will not go."
}
```

此時 console 會印出：

```
I will go, too.
```

如果把 isPeterGoing 改成 false，此時 console 會印出：

```
I will not go.
```
---

### if-else-if statement

讓我們來看 if-else 的最後一個情境：

* 如果湖人贏 10 分，我就賺 100；贏 5 分，賺 50；其他情況我就輸 30。

這種根據多個條件，有多種不一樣的事情要做的狀況，就要利用到 `if-else-if` 語法：

<img src="https://github.com/Wuchiwei/ntu-ios/blob/master/ControlFlow/if-statement/images/if-else-if.png" alt="image" width="500"/>

```swift
var lakerWinScore = 7

if lakerWinScore > 10 {

    print("我賺 100!")

} else if lakerWinScore > 5 {

    print("我賺 50!")

} else {

    print("我輸 30!")
}
```

此時 console 會 print 出：

```
我賺 50!
```

如果把 lakerWinScore 改成 20，此時 console 會印出：

```
我賺 100!
```

---
註：本頁的圖都源自於 [Apple Swift Book](https://docs.swift.org/swift-book/ReferenceManual/Statements.html)
