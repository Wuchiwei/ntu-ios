# Class

將相關聯的資料，放在同一個集合底下，讓我們更順利，更有效的使用資料。

### 宣告語法

```
class 名稱 {

}
```

ex: 
```swift
class Person {

}
```

### Property
我們可以在 class 的 defination 裡面宣告 property，用來儲存資料

ex: 在 class `Person` 裡面 declare 一個 property `name`, data type 為 `String`, 初始值為 `NTU-iOS-Class`

ex: 
```swift
class Person {

    var name: String = "NTU-iOS-Class"
}
```

ex:
```swift
class Classroom {

    var students = ["Ian", "Kevin"]

    var doors = 2

    var teacher: String? = nil

    var temperature
}
```

### Method
我們也可以在 Class defination 裡面定義一個可以重複使用的 function, 稱之為 `method`.

```swift
class Person {

    var name: String = "NTU-iOS-Class"

    func speakName() {

        print("\(name). This is my name.")
    }

    func eat(something food: String) -> String {

        print("I eat \(food).")

        return "\(food) is delicious"
    }
}
```

### Initializer
我們有了 Class 之後，就可以根據這個藍圖，透過 `Initializer`，Create 出許多的 物件 `Instances`.

* **Initializer**: 以 key word `init` 開頭的特殊 `method`
* **Instance**: Class 執行 Initializer 的結果，稱之為 `Instance (物件)`

ex:

```swift
class Person {

    var name: String = "NTU-iOS-Class"

    func speakName() {

        print("\(name). This is my name.")
    }

    func eat(something food: String) -> String {

        print("I eat \(food).")

        return "\(food) is delicious"
    }

    init() {

        print("Here is the initializer in Person class.")
    }

    init(name: String) {

        print("----Initializer with name parameter.----")

        print("Here is the initializer in Person class.")

        self.name = name
    }
}

let luke = Person()

let wayne = Person(name: "wayne")
```

### How to use property and method in Instance

我們宣告一般的 property 跟 method，都必須先產生 Instance 才可以透過 **dot anotation** 去讀取跟使用它.

ex: 
```swift
class Person {

    var name: String = "NTU-iOS-Class"

    func speakName() {

        print("\(name). This is my name.")
    }

    init() {

        print("Here is the initializer in Person class.")
    }
}

let luke = Person()

print(luke.name)

luke.speakName()
```

Console will output:
```
Here is the initializer in Person class.
NTU-iOS-Class
NTU-iOS-Class. This is my name.
```

## Power of Class

讓我們來看看一個新的例子：

```swift
class People {

    let name: String

    var weight: Double

    var height: Double

    init(name: String, width: Double, height: Double) {
        
        self.name = name
        self.width = width
        self.height = height
    }
}

let luke = People(name: "Luke", width: 10.0, height: 10.0)

print(luke.name)
print(luke.width)
print(luke.height)
```

我們把 Luke 的姓名，身高，體重，包在 `luke` 這個 **Instance** 裡面，以後想要找到 luke 的資料，只要找到 `luke` 這個 instance，我就找到有關於 Luke 的所有資料，並不需要再到其他地方找尋資料。透過這個設計方式，**資料被群聚在一起，並賦予了更生動的意義**，這也是物件導向 (Object Orient Programming) 最基本的概念。


### Initializer 的規則

Initializer 有一個規則，就是 Initializer method 執行結束之後，每一個 property 都必須要被適當的安排好，意思是每個 property 都要有 value

所以上面的例子，如果把 `self.height = height` 註解掉，complier 就會報錯，不讓你執行。

```swift
//This is wrong

init(name: String, width: Double, height: Double) {
        
        self.name = name
        self.width = width
        //self.height = height
        //This will cause error occur.
}
```

# Struct
Struct 與 Class 在 Initializer, Property 與 Method，無論是語法，定義，用處，用法，都是完全相同的。


# Struct 與 Class 不同的地方

1. Struct 有一個 Swift 給予的 **Default Initializer**, Class 沒有。

ex: 
```swift

// You will get an error about missing initializer.
class Benz {

    var doors: Int
}

//This is fine.
struct BMW {

    var doors: Int
}

//You will get a free initializer wil all store properties as parameters.
let car = BMW(doors: 4)

```

2. 透過 Class 產生的 Instance 是 Reference Type；透過 Struct 產生出來的是 Value Type.

詳細的說明可以參考我的 Medium 文章

[Reference Type and Value Type](https://medium.com/appworks-school/oop-reference-type-and-value-type-in-memory-b74d4df4bb06)
