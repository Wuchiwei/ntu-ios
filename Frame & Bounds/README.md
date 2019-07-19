# Frame & Bounds

iOS 的座標系，是以左上角為原點 (0,0)，向右，向下為正。

<img src="https://github.com/Wuchiwei/ntu-ios/blob/master/Frame%20%26%20Bounds/images/ios_coordinator_system.png" alt="image" width="500"/>


### SuperView and SubView

View 透過 `addSubView` method，可以把其他 view 加到自身的畫面上。此時被加入的 view 稱為 `SubView`, 而把其他 view 加入的 view 稱之為 `SuperView`。

* 每個 View 都有兩個 property: Frame 與 Bounds。
* Frame 用來決定自身在 SuperView 中的位置，Bounds 用來裝載 SubView。
* 系統會以 SubView's frame 作為依據，將 SubView 放入 SuperView 的 bounds 中。
* SuperView 的 Frame 或 Bounds 改變，都會影響 SubView 在畫面上的位置。但 SubView 卻無法影響 SuperView。

