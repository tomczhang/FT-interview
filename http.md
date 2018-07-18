### 1. 页面从输入url到页面加载完成的流程

### 2. http状态码

* 304/201缓存

### 3. TCP三次握手/四次挥手
TCP提供一种面向连接的，可靠的字节流服务。

三次握手：
1. Client发送包含标志位SYN=1和一个随机的seq的数据包到Server，Client进入SYN_SEND状态
2. Server返回SYN=1，ACK=1，ack=seq+1和一个随机的seq到Client，Server进入SYN_RCVD状态
3. Client检查ack的正确性，再发送ACK=1，ack=seq+1到Server，Server再检查，若正确，那就进入建立状态。

四次挥手：
Server在第二步分两次分别发送ack和标志位FIN，原因是Server向Client发送的数据还没结束。

### 4. HTTP 1.0/1.1/2.0


### 5. HTTPS