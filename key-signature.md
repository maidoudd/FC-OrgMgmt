### 密钥与签名
用户程序可以使用融合云服务的sdk访问服务，sdk会使用密钥对请求进行签名，服务会通过迁移验证请求的身份以及进行授权检查。

#### 密钥(AccessKey)
- 用户可以在[web console](https://cloud-platform.d.xiaomi.net/#/services/user-manage/orgnizations)中为自身创建密钥。
- 用户可以在[web console](https://cloud-platform.d.xiaomi.net/#/services/user-manage/orgnizations)中为[团队](organization.md)下为[用户组](team.md)生成密钥。
- 密钥包括两部分：ID和密钥内容(SecretKey)，统称为AccessKey，用户需要避免AccessKey泄漏。
- AcessKey隶属于某个[Team](team.md)或用户，同一个Team/用户可以生成多个AccessKey。

#### 签名(Signature)
融合云sdk会根据提供的AccessKey为请求计算一个数字签名用于身份认证。
