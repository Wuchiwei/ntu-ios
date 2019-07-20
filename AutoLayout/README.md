# Auto Layout

### Auto Layout 原理

相較於直接指定 View 的 Frame，Auto Layout 的原理是：

> 不直接指定 Frame 的 Value，反而是透過描述 View 於其他 View 之間的關係，接著讓 iOS 系統幫我們算出可以滿足這些條件的 Frame。

* 直接指定 Frame 的問題：在不同 Device 的時候，視覺上的感覺很容易會產生差異。

以下圖為例，同樣的 Frame，在 iPhone SE 就會跑出手機畫面；但在 iPhone Xs Max 看起來就在畫面中間的位置，沒有超出畫面。

<img src="https://github.com/Wuchiwei/ntu-ios/blob/master/AutoLayout/images/problem_with_frame.png" alt="problem_with_frame" width=600/>