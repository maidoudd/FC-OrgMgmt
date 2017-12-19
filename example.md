### 示例
通过一个例子说明如何使用团队管理来实现融合云服务的访问控制。

#### 场景
数据服务组的开发同事希望使用融合云的[文件存储](http://docs.api.xiaomi.net/fds/)来存储和分析程序的日志，简称galaxy-log-analyze项目。

#### 用户
项目相关同事：qiankai,linshangquan,zhangjunbin,shenjiaqi,luxianghao，其中luxianghao负责管理资源。

#### 团队
- 作为项目的资源管理者luxianghao，首先根据需要选择了一个融合云站点，比如“小米-c3”。
- 之后luxianghao在web console中创建一个团队：galaxy-log-analyze；同时在[文件存储](http://docs.api.xiaomi.net/fds/)中创建一个[Bucket](http://docs.api.xiaomi.net/fds/basic-concept.html)：galaxy-log-bucket，日志文件会存储在这个bucket下。
- 项目中，zhangjunbin和shenjiqi负责将日志文件上传到到bucket下，因此luxianghao在galaxy-log-analyze团队下创建一个[Team](team.md): write_team：

    1. 将zhangjunbin和shenjiaqi作为member添加到write_team中。
    2. 在web console中为write_team生成[密钥](key_signature.md)。
    3. 将文件存储中的galaxy-log-bucket的写权限赋予write_team。

- 之后，zhangjunbin和shenjiaqi就可以使用生成的密钥通过sdk向galaxy-log-bucket上传文件了。
- qiankai和linshangquan负责读取galaxy-log-bucket下的文件并进行分析，因此luxianghao在galaxy-log-analyze团队下创建一个[Team](team.md): read_team：

    1. 将qiankai和linshangquan作为member添加到read_team中。
    2. 在web console中为read_team生成[密钥](key_signature.md)。
    3. 将文件存储中的galaxy-log-bucket的读权限赋予read_team。

- 之后，qiankai和linshangquan就可以使用生成的密钥通过sdk从galaxy-log-bucket下载文件了。
- 当有其他同事，比如cuijianwei需要上传文件到galaxy-log-bucket，luxianghao可以将cuijianwei加入到galaxy-log-analyze团队下的write_team中。
- luxianghao也可以在write_team中指定zhangjunbin为write_team的admin，这样zhangjunbin就可以将其他需要上传文件的同事加入到write_team中。

