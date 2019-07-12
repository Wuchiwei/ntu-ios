# Collection Type

Swift 裡 Collection Type 有三種，Array, Dictionary, Set。

<img src="https://github.com/Wuchiwei/ntu-ios/blob/master/DataType/Collection/images/collection.png" alt="image" width="500"/>

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

### Array 練習
現在我們有一個通訊錄，裡面儲存了朋友的名字:

`var contacts = ["Michael", "Julie", "Steven"]`

1. 請幫我新增 Ian 到通訊錄
2. 請幫我移除 Julie
3. 請幫我更新 Steven 為 Steven Choa
4. 請幫我把 Ian 搬到 index 為 0 的位置

# Dictionary

Dictionary 是另外一種可以儲存多筆資料的資料型態；與 Array 不同的是，Dictionary 沒有次序性，它的資料是以 `key-value` 的方式儲存與讀取。

1. Create a Dictionary

```swift
var contacts: [String: Int] = [

    "Luke": 0987654321, 
    "ntu": 27273737
]

let emptyDictionary: [String: String] = [:]
```

其中寫在 `:` 前面的稱之為 **key**，寫在 `:` 後面的稱之為 **value**。

2. Add key value in Dictionary 新增一筆資料

```swift
var contacts: [String: Int] = [

    "Luke": 0987654321, 
    "ntu": 27273737
]

contact["iOS"] = 1234567

```
2. Get value in Dictionary 讀取一筆資料

```swift
var contacts: [String: Int] = [

    "Luke": 0987654321, 
    "ntu": 27273737
]

print(contacts["Luke"])
```

Console will output: 

```
0987654321
```

3. Update value in Dictionary 更新一筆資料

```swift
var contacts: [String: Int] = [

    "Luke": 0987654321, 
    "ntu": 27273737
]

contacts["Luke"] = 34567

print(contacts["Luke"])
```

Console will output: 

```
34567
```

4. Remove a value in Dictionary 移除一筆資料

```swift
var contacts: [String: Int] = [

    "Luke": 0987654321, 
    "ntu": 27273737
]

contacts["Luke"] = nil //這樣就移除 key 為 "Luke" 的這筆資料
```

### Dictionary 練習

我們要建立一個機場全名與縮寫的對照表：

```swift
var airports = [
    "YYZ": "Toronto Pearson", 
    "DUB": "Dublin"
]
```

1. 請讀取 "DUB" 所對應到的全名
2. 新增一筆資料："London" 機場的縮寫為 "LHR"
3. 修改 "LHR" 的 value 為 "London Heathrow"
4. 移除 "YYZ" 這筆對照資料