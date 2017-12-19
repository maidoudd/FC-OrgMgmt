### 密钥与签名
应用程序可以使用融合云服务的sdk访问服务，sdk会使用密钥对请求进行签名，服务会通过签名验证请求的身份并进行授权检查。

#### 密钥(AccessKey)
- User可以在[web console](https://cloud.d.xiaomi.net/#/services/user-manage/orgnizations)中为自身创建密钥，一般用于初始开发的测试环节。
- User可以在[web console](https://cloud.d.xiaomi.net/#/services/user-manage/orgnizations)中为[Org](organization.md)下为[Team](team.md)生成密钥，一般用于后期测试、联调及上线等环节。
- 密钥包括两部分：ID和密钥内容(SecretKey)，统称为AccessKey，用户需要避免AccessKey泄漏。
- AccessKey隶属于某个Team或User，同一个Team或User可以生成多个AccessKey。

#### 签名(Signature)
融合云sdk会根据提供的AccessKey为请求计算一个数字签名用于身份认证。
