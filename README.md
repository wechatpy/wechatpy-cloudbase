# 使用 wechatpy 进行小程序云开发

[云开发（Tencent Cloud Base，TCB）](https://www.cloudbase.net/)是腾讯云为移动开发者提供的一站式后端云服务，它帮助开发者统一构建和管理资源，免去了移动应用开发过程中繁琐的服务器搭建及运维、域名注册及备案、数据接口实现等繁琐流程，让开发者可以专注于业务逻辑的实现，而无需理解后端逻辑及服务器运维知识，开发门槛更低，效率更高。

[wechatpy] 从 1.8.11 版本开始增加了对云开发接口的支持。

## 一、安装依赖

```bash
pip install 'wechatpy[cryptography]'
```

## 二、参数配置

```python
from wechatpy.client import WeChatClient

app_id = '...'  # 微信小程序的 appid
secret = '...'  # 微信小程序的 secret

client = WeChatClient(app_id, secret)
```

## 三、调用云开发接口

云开发接口目前均挂在 `WeChatClient.cloud` 成员实例下，已触发云函数接口为例，可采用如下方式调用：

```python
result = client.cloud.invoke_cloud_function('env_name', 'login', '{}')
```

更多接口可以在 [wechatpy 云开发接口文档](https://wechatpy.readthedocs.io/zh_CN/master/client/cloud.html) 中查阅。

[wechatpy]: https://github.com/wechatpy/wechatpy
