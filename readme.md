# Exercise 1: JavaScript Drum Kit
这段代码是一个简单的 JavaScript 鼓点套件。它使用 HTML，CSS 和 JavaScript 来创建一个用户可以通过键盘进行交互的虚拟鼓套件。

## 要点
HTML 中的每个鼓点都有一个与键盘键对应的 data-key 属性，以及一个对应的音频文件。按键和音频标签都添加了属性`data-key`，用于存储对应的键码，目的是添加键盘事件监听后，触发键盘事件时即可获取事件的`keyCode`属性，然后以此操作对应按键和音频。
```javascript
const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);
const key = document.querySelector(`div[data-key="${e.keyCode}"]`);
```

JavaScript 代码监听键盘的 keydown 事件，当按下对应的键时，会播放相应的音频文件，并给对应的鼓点元素添加 playing 类，使其在视觉上产生反馈。

当 CSS 转换完成后（即鼓点元素的 playing 类产生的动画效果完成后），移除 playing 类，使鼓点元素回到原始状态。

playSound 函数会检查 isPlaying 对象中对应的键是否已经在播放，如果是，就不会再次播放。stopSound 函数会在按键抬起时停止音频播放，并清除 isPlaying 对象中对应的键，表示音频已停止播放。

## 基础语法

- data-key: 自定义的数据属性，用于存储自定义数据。
- classList.add(), classList.remove(): JavaScript 中的方法，用于添加和删除元素的类。
- document.querySelector(): 用于选择文档中的元素。
- addEventListener(): 用于添加事件监听器。
- e.keyCode: 事件对象的属性，表示触发事件的键的键码。
- audio.play(), audio.pause(): HTMLMediaElement 的方法，用于播放和暂停音频/视频。
- audio.currentTime: HTMLMediaElement 的属性，用于获取和设置音频/视频的当前播放位置。
- window: 代表浏览器窗口，是所有全局 JavaScript 对象、函数和变量的容器。