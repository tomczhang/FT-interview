### 1. CSS盒子模型
标准盒子模型：盒子占位width = content + 2margin + 2padding + 2border
怪异盒子模型：盒子占位width = content + 2margin。content部分包含了 border 和 pading。

border-sizing：border-box；可以用来设置怪异盒子模型。

弹性盒子模型：
flex-direction：row/column;
flex-wrap：no-wrap/warp;
justify-content:space-between/flex-start/space,align-items:center,flex-grow，flex:2 1

### 2. BFC
BFC: 块级格式上下文。BFC就是一个页面上独立的容器，规定了内部的块级元素如何布局，并且这些块级元素不会影响外部元素。

BFC的作用：
* 自适应两栏布局
* 清除浮动
* 防止垂直margin重叠

BFC的生成条件：
* 根元素
* overflow不为visible
* float不为none
* position属性为absolute/fixed
* display为inline-block, table-cell, table-caption, flex, inline-flex

### 3. 清除浮动
方法如下：
* 父元素BFC overflow:hidden
* 新增底部兄弟元素 clear:both 块级元素的左右都不能有浮动元素
* 添加自身伪元素 伪元素是元素的子元素，在元素的内容之前或者之后

```
.clearfix::after {
    content: '';
    display: block;
    clear: both;    
}
```
### 3. 页面自适应/响应式设计/移动适配
设置理想视口：
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">

方法：
* rem: fontSize = window.innerWidth / 7.5 + 'px'
* flexible: 为了解决小于1px的展示问题。将视口分成了10rem。不兼容响应式布局。
* vw: flexible是vw的hack写法。Viewport Units Buggyfill用来做android兼容。

### 4. CSS水平/垂直居中
* 水平居中方法
    * text-align:center;
    * margin: 0 auto;
    * 有固定宽度，position:relative;left:50%;margin-left: -1/2宽度;
    * CSS3，position:relative;left:50%;transform:translateX(-50%);
* 垂直居中方法：
    * vertical-align:middle;
    * line-height和height同高
    * display:flex;align-items:center;
    * CSS3，position:relative;top:50%;transform:translateY(-50%);
    * 有固定高度，postion:absolute/fixed;top:50%;margin-top: -1/2高度;
    * display:table-cell;vertical-align:middle;
    *    parent:after {content:'';display:inlineblock;verticalalign:middle;height:100%;width:0}
    
    son {display:inline-block;vertical-align:middle}

### 5. CSS预处理器/后处理器
**预处理器：less, sass**
作用：
* 增加复用性：定义变量，混合宏mixin，继承
* 增加便利性：添加前缀，自动添加兼容性，函数式使用，递归式定义

**后处理器：postcss**
作用：
* 针对浏览器兼容 postnext, autoprefix
* 针对css优化 cssnano
* 提高开发效率

### 6. CSS优化
* CSS压缩
* CSS合并
* 首屏CSS拆分
* 尽量使用最准确的选择器
* 避免使用后代选择器
* 减少重排：不要使用table布局，大量DOM操作离线处理，不要随便改变dom树的结构
* 减少重绘
* 不用CSS filters，少用transform，box-shadows

### 7. 写一个滚动，写一个轮播，写一个三角形

### 8. 伪类/伪元素
> 伪类：伪类用于当已有元素处于的某个状态时，为其添加对应的样式，这个状态是根据用户行为而动态变化的。
伪元素：伪元素用于创建一些不在文档树中的元素，并为其添加样式。

![](/assets/WechatIMG89.jpeg)

