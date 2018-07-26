### 设计模式

#### 单例

```
    class ProxysingletonCreateDiv {
        constructor(htmlStr) {
            return ProxysingletonCreateDiv.getInstance(htmlStr);
        }
        static getInstance(name) {
            if(!ProxysingletonCreateDiv.instance) {
                ProxysingletonCreateDiv.instance = new CreateDiv(name)
            }
            return ProxysingletonCreateDiv.instance;
        }
    }
```

#### 工厂

#### 观察者