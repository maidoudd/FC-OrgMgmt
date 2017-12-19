### 访问方式
支持Web console登录和sdk访问两种方式。

#### Web console登录
- Web console地址为：https://cloud.d.xiaomi.net
- User可以通过公司邮箱的帐号和密码登录Web console。
- Web console提供融合云的团队管理功能，User可以在Web console里创建[Org](organization.md)/[Team](team.md)/[AccessKey](key_signature.md)；此外，User可以通过Web Console访问融合云的各个服务、查看文档、查看统计指标等。

#### sdk访问
- 融合云各个服务都提供了不同语言的sdk，User的程序可以使用sdk来访问服务。
- User需要在Web console中生成[AccessKey](key_signature.md)，sdk会使用AccessKey对访问进行签名，服务根据签名来认证请求身份。
