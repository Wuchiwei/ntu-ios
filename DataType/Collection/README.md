# Collection Type

Swift 裡 Collection Type 有三種，Array, Dictionary, Set。

# Array

如果我們要算兩個數的平均，我們應該會這樣寫：

```swift
let a = 10
let b = 20

let sum = (a + b) / 2
```

我們用了兩個變數 `a`, `b`，儲存了兩個數，然後算平均。

那如果我們要算三個數的平均呢？就要再多一個變數。

```swift
let a = 10
let b = 20
let c = 30


let sum = (a + b + c) / 3
```

你會發現，為了處理更多的數，我們將會使用更多的變數，這其實挺困擾的。幸好 Swift 出了另外一種儲存資料的型態 `Array`

`Array` 的概念是它會將資料有順序的儲存好，我們可以從第一個，依序找到最後一個元素。

讓我們來看看如何宣告一個 `Array`

```swift

var musics: Array<String> = ["1", "2", "3"]

var youtubers: [String] = ["聖", "火", "尊", "玉"] //Preferred

print(musics[0]) //1

print(musics[1]) //2

print(musics[2]) //3

print(musics[0]) //聖

print(musics[1]) //火

print(musics[2]) //尊

print(musics[3]) //玉

```

以上兩種寫法都宣告了一個 element 為 String 的 array；而後面的 `["1", "2", "3"]` 與 `["聖", "火", "尊", "玉"]` 則是實際的資料。

我們可以透過給予 `index` 的方法，存取裡面的資料，在變數後面加上 `[]`，並在中間放入 `index`，指定我們要的 element 位於哪一個位置。


**Array Rules:**

1. 同一個 array 裡面只能接受同一種 type 的 element

ex: 

```swift
var number: [Int] = [1, 2, "3"] //fail, 3 不是 Int
```

2. Array index 從 **0** 開始。

ex: 

```swift
var names: [String] = ["Sylvia", "Andy", "Mike"]

print(names[0])  
```

Console will output:

```
Sylvia
```

3. 不可以讀取超過 Array element 數量的 index

```swift
var number: [Int] = [1, 2, 3]

print(number[3]) //crash：Index out of range。Array 只有 3 個數，所以 index 最大只到 2。index 3 超出範圍了。
```

### Operate with Array 

```swift
var names: [String] = ["Sylvia", "Andy", "Mike"]
```

1. Read 讀取

```swift
let friend = names[1] // friend will be "Andy"
```

2. 更新 Update

```swift
names[2] = "Luke"

//After this, array will be ["Sylvia", "Andy", "Luke"]
```

3. Add 新增

```swift
names.append("Henry")

//After this, array will be ["Sylvia", "Andy", "Luke", "Henry"]

names = names + ["Alex"]

//After this, array will be ["Sylvia", "Andy", "Luke", "Henry", "Alex"]
```

4. Remove 移除

```swift
names.remove(at: 2)
//After this, array will be ["Sylvia", "Andy", "Henry", "Alex"]
```

### 練習
現在我們有一個通訊錄，裡面儲存了朋友的名字:

`var contacts = ["Michael", "Julie", "Steven"]`

1. 請幫我新增 Ian 到通訊錄
2. 請幫我移除 Julie
3. 請幫我更新 Steven 為 Steven Choa
4. 請幫我把 Ian 搬到 index 為 0 的位置


