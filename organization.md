### 团队（Organization/Org）
即业务团队，提供资源计费和访问控制功能：
- 团队管理的Web console页面是：https://cloud-platform.d.xiaomi.net/#/services/user-manage/orgnizations。
- 资源：融合云系统中的资源，包括但不限于[文件系统](http://docs.api.xiaomi.net/fds/)中的文件，[结构化存储](http://docs.api.xiaomi.net/sds/)的表等，资源可以认为是融合云服务能力的抽象。
- 用户可以创建团队，每个创建的团队是跨[Region](region.md)全局唯一的。
- 用户在创建团队时，用户自动作为团队的Admin，创建者可以添加其他用户为团队Admin。
- 团队的Admin可以在团队下创建[用户组/Team](Team.md)，Team是资源权限授予的grantee。
- 团队的Admin可以为团队下其它Team授予“可创建资源”权限，被授权的Team就可以在团队下创建资源。
- 用默认情况下，用户创建的资源隶属于用户自身；用户在创建资源时，可以选择创建在某个有“可创建资源”权限的团队，这样资源就隶属于团队。
- 融合云会根据资源的使用情况对资源进行计费，计费的结果会汇总到资源隶属的用户或团队下。
