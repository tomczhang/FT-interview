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
核心：工厂实现决定如何实例化产品，是实现扩展的途径，需要有多少种产品，就需要有多少个具体的工厂实现
直接使用ES6继承实现

#### 观察者
