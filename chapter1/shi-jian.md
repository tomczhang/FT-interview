### 7. 事件冒泡/捕获/委托/广播

事件冒泡：事件最开始以具体的元素接收，然后逐级向上传播到不具体的节点。
事件捕获：事件最开始被不太具体的节点捕获，然后逐级向下传递给具体的节点。
事件委托：只定义一个类型的事件处理程序，就可以管理某一个类型所有的事件。
事件广播：elem.dispatchEvent(event)。

event.preventDefault(): 取消事件的默认行为
event.stopPropagation(): 阻止事件的进一步捕获或冒泡
使用document.createEvent()来模拟和创造自定义事件

window.load: 会在页面一切资源家在完毕后触发
DOMContentLoaded: DOM结构绘制完毕后就触发，如同$(document).ready()


### 8. 事件循环/异步


### 8. 缓存

浏览器缓存：bfcache

#### 8.1 BFcache: 往返缓存。

相关事件：
* pageshow: 没有BFcache时，这个事件会在load事件触发后触发，有BFcache时，会在页面状态完全恢复的那一刻触发。事件的目标是document，但是要绑定在windows上。
  pageshow事件还有一个persisted属性，可以用来表征是否使用了BFcache，true代表使用。

* pagehide: 会在浏览器卸载页面的时候触发，而且是在unload事件之前触发。

去除BFcache的相关方法：
1. 判断pageshow的event.persisted，如果true就页面重载
2. 设置页面的onunload页面事件监听




