# For-In Loops

For-In Loop 可以讓我們透過簡單幾行的程式碼，讓電腦幫我們重複做一些事情。

### Use For-In Loops with Array

```swift
let names: [String] = ["Anna", "Alex", "Brain", "Jack"]

for name in names {

    print("Hello, \(name)!")
}
```
**Explain:**

Array 裡面的每一個元素，會被輪流放進 `name` 這個元素裡面，**並執行兩個大括號裡面的程式碼一次**。以這個範例為例，`print("Hello, \(name)!")` 會被執行 4 次，因為 array 裡面有 4 個元素。

`name`: 用來代表 array 裡面的當輪元素。

### 練習

1. `let scores = [10, 20, 30, 40, 10]`，請算出 array 裡面的元素總和。
2. `let heights = [175, 170, 200, 160]` 請算出身高大於 `165` 的人數
3. `let names = ["John", "Mary", "John", "Browm", "Mike"]` 請問 array 裡有幾個 `John`?
4. `let numbers = [1, 2, 3, 4, 5]` 請產生一個 array, 裡面的 element 是 `numbers` 裡面每個 element 的平方數。

### Use For-In Loops with Dictionary

使用 for loop 與 dictionary，因為 dictionary 是 `key-value` pair，所以前面代表這個 pair 的位置，要有兩個變數。Dictionary 裡面的 **每一對 key-value**，會被輪流放進前面的變數裡面，**並執行兩個大括號裡面的程式碼一次**。

```swift
for (key, value) in Dictionary {
    //...write something here
}
```

```swift
let numberOfLegs = ["spider": 8, "ant": 6, "cat": 4]

for (animalName, legCount) in numberOfLegs {
    
    //This print statements will be excute 3 times.
    print("\(animalName)s have \(legCount) legs")
}
```

### Use For-In Loops with Ranges

**Range** : 以 `...` 來表示，有兩種選項可以運用：
1. 0...3 代表 0, 1, 2, 3
2. 0..<3 代表 0, 1, 2 (不包含 upper bounds)

```swift
for index in 1...5 {
    print("\(index) times 5 is \(index * 5)")
}
```

Console will output:
```
1 times 5 is 5
2 times 5 is 10
3 times 5 is 15
4 times 5 is 20
5 times 5 is 25
```

```swift
for index in 1..<5 {
    print(index)
}
```

Console will output:
```
1
2
3
4
```

* 如果你不需要前面的變數，也可以用 `_` 代替：

```swift
let base = 3
let power = 4
var answer = 1
for _ in 1...power {
    answer *= base
}
print("\(base) 的 \(power) 次方是 \(answer)")
```

Console will output:
```
3 的 4 次方是 81
```

* Range 也可以放入變數

```swift
let start = -1

let end = 3

for tickMark in start..<end {
    
}
```

Console will output:
```
-1
0
1
2
```

### Stride (傳統的 for in loop)

* 不包含上限，使用 `(from:to:by)`

```swift
for i in stride(from: 0, to: 10, by: 2) {
    
    print(i)
}
```

Console will output:
```
0
2
4
6
8
```

* 包含上限，使用 `(from:through:by)`

```swift
for i in stride(from: 10, through: 0, by: -2) {
    
    print(i)
}
```

Console will output:
```
10
8
6
4
2
0
```