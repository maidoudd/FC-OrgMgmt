### Org
即业务部门（Organization），提供资源计费和访问控制功能：
- 团队管理的Web console页面是：https://cloud.d.xiaomi.net/console/#/services/user-manage/orgnizations
- 资源：融合云系统中的资源，包括但不限于[文件存储](http://docs.api.xiaomi.net/fds/)中的文件，[结构化存储](http://docs.api.xiaomi.net/sds/)中的表等，资源可以认为是融合云服务能力的抽象。
- [User](user.md)可以创建Org，每个创建的Org是跨[Region](region.md)全局唯一的。
- User在创建Org时，User会自动成为Org的Admin，创建者可以添加其他User为Org的Admin。
- Org的Admin可以在Org下创建[Team](Team.md)，Team是资源权限授予的grantee。
- Org的Admin可以为Org下其他Team授予“可创建资源”权限，被授权的Team就可以在Org下创建资源。
- User在创建资源时，默认情况下所创建的资源隶属于User自身，如果选择了创建在某个有“可创建资源”权限的Org，则资源就隶属于该Org。
- 融合云会根据资源的使用情况对资源进行计费，计费的结果会汇总到资源隶属的User或Org下。
