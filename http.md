### 1. 页面从输入url到页面加载完成的流程
1. 浏览器开启一个线程处理请求，根据协议选择不同的处理方式
2. 应用层 域名解析 本地DNS缓存，DNS服务器—>根域名服务器->顶级域名服务器->特定域名服务器
3. 网络层 通过IP地址寻找服务器的物理地址
4. 网络传输层 通过三次握手建立TCP连接
5. 网络链路层 将数据包封装成帧
6. 物理层利用物理介质进行传输
7. 到了服务器之后将数据一层层还原成原来的格式
8. 服务器进行安全验证，跨域验证，验证不通过就反回相应的报文
9. 验证通过，后台经过处理后返回数据
10. 下载数据
11. 浏览器有缓存，304，浏览器使用本地缓存 与之对应的是200 静态文件缓存，不请求服务器 Apache/nginx设置 静态文件后面加参数 304
12. 没有缓存的话，接到响应就开始下载资源/网页
13. 网页会被浏览器内核进行处理
    * 根据Doctype决定解析方式
    * GUI渲染线程解析html，构建DOM树
    * GUI渲染线程和JS引擎是互斥的，遇到JS解析之后就等待JS解析，然后再继续渲染
    * CSS和图片是异步的，不会阻塞DOM树的构建
    * CSS解释器会生成CSS规则树，然后合并两个树生成render树
    * 对render树进行布局和绘制
    
### 2. http状态码

* 1xx：临时响应
100: 继续请求。早期某些浏览器的post请求
* 2xx：成功
200：服务器成功处理请求
* 3xx：重定向
301：永久重定向。客户端应当保存新的链接
302：临时重定向。
* 4xx：请求错误
401：未授权，要求身份验证
403：服务器禁止请求
404：服务器找不到请求的网页
* 5xx：服务器错误
500：服务器内部错误
502：错误网关
504：网关超时

### 3. TCP三次握手/四次挥手
TCP提供一种面向连接的，可靠的字节流服务。

三次握手：
* 客户端：你是XXX服务端吗？
* 服务端：我是XXX服务端，你是客户端吗？
* 客户端：是的，我是客户端
建立连接成功后，接下来就可以进行正式的传输数据。

四次挥手：
* 主动方：我已经关闭了向你那边的信息发送通道，只能被动接受信息了；
* 被动方：收到通道关闭的信息；
* 被动方：我现在也关闭了向你那边发送信息的通道
* 主动方：我收到信息，连接断开，之后双方无法通信

### 4. HTTP 1.0/1.1/2.0
* HTTP 1.1 
长链接，Host头处理，断点续传
* HTTP 2.0
多路复用，服务器推送，header头压缩，请求优先级，二进制分帧

### 5. HTTP/HTTPS
* http是明文传输，连接是无状态的，https是ssl加密的安全协议，可以进行加密传输，身份验证
* 使用完全不同的连接模式，端口号是80 443

### 6. Doctype
Doctype声明告知浏览器哪种HTML或XHTML规范解析页面。

html4基于SGML（标准通用标记语言），所以要用DTD（文档类型定义）进行引用。

### 7. HTML5新特性
* 新的选择器document.querySelector/All
* 拖拽api
* Canvas
* Video, audio
* 离线存储
* 语义化标签
* 增强表单控件
* 地理位置Geolocation
* 双工通信协议websocket
* 多任务webworker


