### 请求方式
* Axios:
   * 可以在node和浏览器中使用，支持Promise API
   * 可以取消请求
   * 可以拦截请求
   * 可以客户端抵御CSRF攻击
   * 可以转化请求和响应数据
   
* Fetch:
   * 可以在node和浏览器中使用，支持Promise API
   * 新的底层逻辑，不再使用xhr
   * 可以用来简单跨域 mode: 'no-cors', 返回一个type为“opaque”请求返回
   * fetch只对网络请求报错，对400，500都当做成功的请求，需要封装去处理
   * fetch不支持中断请求
   * fetch默认不会带cookie
   * fetch不能进行请求进度的检测
   
 * XHR
   ```
   var xhr;
    if(window.XMLHttpRequest){
        xhr = new XMLHttpRequest();
    }else{
        xhr = new ActiveXObject('Microsoft.XMLHTTP');
    }
    //发送请求
    xhr.open('get','/uploads/rs/26/ddzmgynp/message.xml',false);
    xhr.send();
    //同步接受响应
    if(xhr.readyState == 4){
        if(xhr.status == 200){
            //实际操作
            result.innerHTML += xhr.responseText;
        }
    }
   ```