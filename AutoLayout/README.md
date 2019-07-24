# Auto Layout

### Why we need Auto Layout?

相較於直接指定 View 的 Frame，Auto Layout 的原理是：

> 不直接指定 Frame 的 Value，反而是透過描述 View 於其他 View 之間的關係，接著讓 iOS 系統幫我們算出可以滿足這些條件的 Frame。

### 直接指定 Frame 的問題：在不同 Device 的時候，視覺上的感覺很容易會產生差異。

以下圖為例，同樣的 Frame，在 iPhone SE 就會跑出手機畫面；但在 iPhone Xs Max 看起來就在畫面中間的位置，沒有超出畫面。

<img src="https://github.com/Wuchiwei/ntu-ios/blob/master/AutoLayout/images/problem_with_frame.png" alt="problem_with_frame" width=600/>

### Auto Layout 原理

描述每個元件，水平或是垂直關係，並有 constant 跟 multiplier 兩個參數可以做調整。

<img src="https://github.com/Wuchiwei/ntu-ios/blob/master/AutoLayout/images/auto_layout_formula.png" alt="auto_layout_formula" width=600/>

可以做關聯的 Attribute 組合：

<img src="https://github.com/Wuchiwei/ntu-ios/blob/master/AutoLayout/images/auto_layout_attribute.png" alt="auto_layout_attribute" width=600/>

[Reference: Apple Auto Layout Guide](https://developer.apple.com/library/archive/documentation/UserExperience/Conceptual/AutolayoutPG/AnatomyofaConstraint.html#//apple_ref/doc/uid/TP40010853-CH9-SW1)

### Safe Area

每個機型，上下需要留白的大小都不相同，還會有 UINavigationBar 跟 UITabBar 高度不同的問題，所以 Apple 提供了 Safe Area 這個元素，搭配 Auto Layout 讓系統自動幫我們處理這個問題。

<img src="https://github.com/Wuchiwei/ntu-ios/blob/master/AutoLayout/images/safe_area.png" alt="safe_area" width=600/>

# 練習 
[影片詳解](https://youtu.be/Nqt1lAGpJAo)

1. 建立一個 View 距離螢幕:
   * Leading 30 pts
   * Safe Area Top 100 pts
   * Trailing 30 pts
   * Height 100 pts 

2. 建立一個 View :
   * Center X 在畫面正中間
   * Center Y 在畫面正中間
   * Width 100 pts
   * Height 100 pts 

3. 建立一個 View 距離螢幕:
   * Top 在螢幕的垂直正中間
   * Bottom 在畫面最下方（非 Safe Area）
   * Leading 100 pts
   * Width 100 pts

4. 建立一個 View 距離螢幕:
   * Width 是螢幕 Width 的 1/2
   * Height 是螢幕 Height 的 1/2
   * Leading 100 pts
   * Top 100 pts

5. 建立一個 View 距離螢幕:
   * Width 是螢幕 Width 的 1/2
   * 寬高比 4:3
   * Leading 在螢幕 1/4 的地方
   * Bottom 與螢幕的 Bottom 貼齊
