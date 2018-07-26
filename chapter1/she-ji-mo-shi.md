### 设计模式

#### 单例

核心：使用闭包保存实例对象，若实例对象存在，则直接返回实例对象。
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