# learn iam
### 01 | IAM系统概述
* IAM（Identity and Access Management，身份识别与访问管理）系统是用 Go 语言编写的一个 Web 服务，用于给第三方用户提供访问控制服务。
    * 对访问进行认证
    * 对资源进行授权
![IAM 系统的完整架构](https://static001.geekbang.org/resource/image/0a/42/0a5f6fd67af1eda1c690c8216dc5e042.jpg?wh=3197*2063)
![组件和功能](https://static001.geekbang.org/resource/image/6c/71/6cdbde36255c7fb2d4f2e718c9077a71.jpeg?wh=1920*1043)
* IAM 系统的资源授权的流程
    ![资源授权的流程](https://static001.geekbang.org/resource/image/ee/50/eed75fcd91d6e726ca74315d65193150.jpg?wh=2513*1134)
    1. 用户需要提供昵称、密码、邮箱、电话等信息注册并登录到 IAM 系统，这里是以用户名和密码作为唯一的身份标识来访问 IAM 系统，并且完成认证。
    2. 因为访问 IAM 的资源授权接口是通过密钥（secretID/secretKey）的方式进行认证的，所以用户需要在 IAM 中创建属于自己的密钥资源。
    3. 因为 IAM 通过授权策略完成授权，所以用户需要在 IAM 中创建授权策略。
    4. 请求 IAM 提供的授权接口，IAM 会根据用户的请求内容和授权策略来决定一个授权请求是否被允许。
* 3 种 RESTful 资源
    * 用户（User）：实现对用户的增、删、改、查、修改密码、批量修改等操作。
    * 密钥（Secret）：实现对密钥的增、删、改、查操作。
    * 策略（Policy）：实现对策略的增、删、改、查、批量删除操作。
* IAM 软件架构模式:前后端分离架构
![前后端分离架构](https://static001.geekbang.org/resource/image/a2/76/a2e1f1cc135debd86611yya1f221c476.jpg?wh=2519*1447)
---
### 02 | 环境准备