## 运行示例

### 分别运行创建的生产者和订阅者服务

- 1.默认主题发布消息测试

打开postman,post提交url请求（http://localhost:8081/sendMqtt?msg=哈哈哈）或用其它工具提交以下代码

```js
var settings = {
  "url": "http://localhost:8081/sendMqtt?msg=哈哈哈",
  "method": "POST",
  "timeout": 0,
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

观察订阅者项目控制台，会有以下消息输出：

```
--------------------START-------------------
接收到订阅消息:
topic:topic_default
message:哈哈哈
---------------------END--------------------
```

表示订阅者成功收到了发布者发布的消息

- 2.自定义主题发布消息测试

打开postman,post提交url请求（http://localhost:8081/sendMqtt2?topic=yuntian&msg=哈哈哈）或用其它工具提交以下代码

```js
var settings = {
  "url": "http://localhost:8081/sendMqtt2?topic=yuntian&msg=哈哈哈",
  "method": "POST",
  "timeout": 0,
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

观察订阅者项目控制台，会有以下消息输出：

```
--------------------START-------------------
接收到订阅消息:
topic:yuntian
message:哈哈哈
---------------------END--------------------
```

表示订阅者成功收到了发布者发布的yuntian主题消息
