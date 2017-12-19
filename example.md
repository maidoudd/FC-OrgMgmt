### 使用示例
通过一个例子说明如何使用团队管理来实现融合云服务的访问控制。

#### 场景
数据服务组的开发同事希望使用融合云的[文件存储](http://docs.api.xiaomi.net/fds/)来存储和分析程序的日志，简称galaxy-log-analyze项目。

#### User
项目相关同事：user1,user2,user3,user4,user5，其中user5负责管理资源。

#### Org
- 作为项目的资源管理者user5，首先根据需要选择了一个融合云Region，比如“小米-c3”。
- 之后user5在web console中创建一个Org：galaxy-log-analyze；同时在[文件存储](http://docs.api.xiaomi.net/fds/)中创建一个[Bucket](http://docs.api.xiaomi.net/fds/basic-concept.html)：galaxy-log-bucket，日志文件会存储在这个bucket下。
- 项目中，user3和user4负责将日志文件上传到bucket下，因此user5在galaxy-log-analyze这个Org下创建一个[Team](team.md): write_team：

    1. 将user3和user4作为member添加到write_team中。  
    2. 在web console中为write_team生成[AccessKey](key-signature.md)。  
    3. 将文件存储中的galaxy-log-bucket的写权限赋予write_team。  

- 之后，user3和user4就可以使用生成的AccessKey通过sdk向galaxy-log-bucket上传文件了。
- user1和user2负责读取galaxy-log-bucket下的文件并进行分析，因此user5在galaxy-log-analyze这个Org下创建一个[Team](team.md): read_team：

    1. 将user1和user2作为member添加到read_team中。  
    2. 在web console中为read_team生成[AccessKey](key-signature.md)。  
    3. 将文件存储中的galaxy-log-bucket的读权限赋予read_team。  

- 之后，user1和user2就可以使用生成的AccessKey通过sdk从galaxy-log-bucket下载文件了。
- 当有其他同事，比如user6需要上传文件到galaxy-log-bucket，user5可以将user6加入到galaxy-log-analyze这个Org下的write_team中。
- user5也可以在write_team中指定user3为write_team的admin，这样user3就可以将其他需要上传文件的同事加入到write_team中。

