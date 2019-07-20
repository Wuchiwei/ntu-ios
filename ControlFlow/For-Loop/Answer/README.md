9. 請設計一個 For loop, 會從 0 執行到 100，3 的倍數輸出 Fizz，5 的倍數輸出 Buzz，既是 3 也是 5 的倍數輸出 Fizz Buzz。

```swift
//Single if statement
for i in 0...100 {

    if i % 15 == 0 {

        print("\(i) Fizz Buzz")

        continue
    }

    if i % 3 == 0 {

        print("\(i) Fizz")

        continue
    }

    if i % 5 == 0 {

        print("\(i) Buzz")
    }
}

// OR use if-else-if
for i in 0...100 {
    
    if i % 5 == 0 {
        
        print("\(i) Buzz")
    
    } else if i % 3 == 0 {
        
        print("\(i) Fizz")
    
    } else if i % 15 == 0 {
        
        print("\(i) Fizz Buzz")
    }
}
```