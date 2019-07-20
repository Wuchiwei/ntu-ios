# Frame & Bounds

iOS 的座標系，是以左上角為原點 (0,0)，向右，向下為正。

<img src="https://github.com/Wuchiwei/ntu-ios/blob/master/Frame%20%26%20Bounds/images/ios_coordinator_system.png" alt="image" width="500"/>


### SuperView and SubView

View 透過 `addSubView` method，可以把其他 view 加到自身的畫面上。此時被加入的 view 稱為 `SubView`, 而把其他 view 加入的 view 稱之為 `SuperView`。

* 每個 View 都有兩個 property: **Frame** 與 **Bounds**。
* Frame 與 Bounds 都是由四個成分所組成：x, y, width, height。
* View 的 Frame 用來決定自身在 SuperView 中的位置: 以 SuperView 的右上角為參考點，決定自己在 SuperView 中的位置

1. 如果 BlueView 的 **SuperView** 是 `BlackView`，則 BlueView 的位置，會在 `case 1` 的地方。
2. 如果 BlueView 的 **SuperView** 是 `RedView`，則 BlueView 的位置，會在 `case 2` 的地方。

<img src="https://github.com/Wuchiwei/ntu-ios/blob/master/Frame%20%26%20Bounds/images/frame_in_different_superview.png" alt="frame_in_different_superview" width="600"/>

* Bounds 則像是一張很大的畫布，用來放置 SubView。系統會以 SubView's Frame 作為依據，將 SubView 以適當的位置，置於 SuperView's Bounds 中。
* SuperView 的 Frame 或 Bounds 改變，都會影響 SubView 在畫面上的位置。但 SubView 的 Frame 與 Bounds 的變化，是不會影響 SuperView 的。