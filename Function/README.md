# Function 函式

將一段程式碼片段，收集起來，加以重複利用。

```
func 函式名稱 (外部參數名稱 內部參數名稱: 資料型別) -> 回傳值型別 {

}
```

ex: 

```swift
func remove(at index: Int) -> Bool {

}
``` 

* 函式名稱: `remove`
* 外部參數名稱: `at` 
* 內部參數名稱: `index`
* 資料型別: `Int`
* 回傳值型別: `Bool`

ex: 

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

可以改寫成

```swift

func outputSlash() {

    print("-------------------")
}

var isRaining: Bool = true

outputSlash()
print("Before if statement")

if isRaining {

    print("I don't want to go outside.")
}

outputSlash()
print("After if statement")
```

再改多一點

```swift
func outputSlash(with text: String) {

    print("-------------------")
    print(text)
}

var isRaining: Bool = true

outputSlash(with: "Before if statement")

if isRaining {

    print("I don't want to go outside.")
}

outputSlash(with: "After if statement")
```

### Function with Return Type

```swift
func sayHello(to name: String) -> String {
    
    return "Hello, \(name)"
}

let text = sayHello(to: "iOS")

print(text)
```

Console will output:
```
Hello, iOS
```

### Default value

```swift
func sayHello(to name: String = "world") -> String {
    
    return "Hello, \(name)"
}

let text = sayHello()

print(text)
```

Console will output:
```
Hello, world
```

### Mutiple parameter 多個參數

```swift
func greet(person: String, alreadyGreeted: Bool) -> String {

    if alreadyGreeted {
    
        return greetAgain(person: person)
    
    } else {
    
        return greet(person: person)
    }
}

print(greet(person: "Tim", alreadyGreeted: true))
// Prints "Hello again, Tim!"
```

### Function Without Return Value 沒有回傳值的 Function

```swift
func greet(person: String) {
    
    print("Hello, \(person)!")
}

greet(person: "Dave")
// Prints "Hello, Dave!"
```

# 練習
1. 請宣告一個 function，名字為 `min`, 可以接受兩個為 `Int` 的參數傳入，並 return 較小的那一個。

2. 請宣告一個 function `ascending`，輸入為一個 `[Int]`, 外部參數名稱為 `array`, 內部參數名稱為 `input`, 回傳型別為 `[Int]`。這個 function 的功能為，將一個隨機排序的 array，進行升冪排列，並回傳出來。

    ex: `[10, 9, 8, 7, 6]` 應產生 `[6, 7, 8, 9, 10]` 的結果

3. 請宣告一個 function `reverse`，輸入為一個 `[Int]`, 沒有外部參數名稱為, 內部參數名稱為 `input`, 回傳型別為 `[Int]`。這個 function 的功能為，將一個隨機排序的 array，進行反轉排列，並回傳出來。

4. 請宣告一個 function `hasEven`，輸入為一個 `[Int]`, 沒有外部參數名稱為, 內部參數名稱為 `input`, 回傳型別為 `Bool`。這個 function 的功能為，是判斷輸入的 array 有沒有偶數在裡面，如果有就 return true, 沒有就 return false。

5. 請宣告一個 function `multiple`，輸入為兩個 `Int`, 沒有外部參數名稱為, 內部參數名稱為 `a` ,`b`, 回傳型別為 `Int`，並給予 `b` 預設值 10。這個 function 的功能為將輸入的兩數相乘之後在 return 出來。