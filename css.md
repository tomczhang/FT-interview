### 1. CSS盒子模型
标准盒子模型，怪异盒子模型，border-sizing：border-box

弹性盒子模型：
flex-direction,flex-wrap,justify-content:space-between,align-items:center,flex-grow，flex:2 1

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
* 添加自身伪元素


```
.clearfix::after {
    content: '';
    display: block;
    clear: both;    
}
```






### 3. 页面自适应，响应式设计


### 4. CSS垂直居中

### 5. 浮动，消除浮动，BFC

### 6. CSS预处理器

### 7. CSS优化

### 8. 写一个滚动，写一个轮播，写一个三角形

### 9. 伪类/伪元素

### 10. Chrome支持12px的文字
