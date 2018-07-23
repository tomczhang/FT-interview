### 6. 事件
* 事件捕获/冒泡/代理/委托/广播
* 事件循环

事件冒泡：事件最开始以具体的元素接收，然后逐级向上传播到不具体的节点。
事件捕获：事件最开始被不太具体的节点捕获，然后逐级向下传递给具体的节点。

event.preventDefault(): 取消事件的默认行为
event.stopPropagation(): 阻止事件的进一步捕获或冒泡

window.load: 会在页面一切资源家在完毕后触发
DOMContentLoaded: DOM结构绘制完毕后就触发，如同$(document).ready()



