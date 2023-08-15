一、判断题
1.Java 是编译型语言。
*错，java不是严格的编译型语言，也不是解释型语言。*

2.Javascript 中，不区分大小写字母，也就是说 A 和 a 是同一个变量。
*错，javascript严格区分大小写。*

3.Javascript 中的常量包括 String、Number、Boolean、Null、Undefined。
*错，常量就三种数字Number，字符串String，布尔字面量Boolen*

4.String 字符串的语法中既可以使用单引号，也可以使用双引号。
*正确*

5.typeof 是用来判断变量类型，不可以当作运算符使用。
*错误，可以当运算符使用，可以获取一个值的类型。*

6.任何值和 undefined 运算，undefined 可看做 0 运算。
*错，任何数据类型和undefined运算，都是NaN*

二、请分别描述下列代码中“+”的作用。
1.console.log(“年龄:” + 20);
*连字符 输出结果：年龄：20*

2.console.log(11+22+33);
*运算符加号 输出结果：66*

3.console.log(“网络 + 安全”);
*字符串 输出结果：网络 + 安全*

4.var a = 1;
var b = 2;
console.log(“a” + b);
*连字符 输出结果：a2*

5.var a = 1;
var b = 2;
console.log(“a + b”); 
*字符串，输出结果：a + b*

三、计算下述代码的打印值
var a = 10;
var b = 10;
console.log(a++);
console.log(++a);
console.log(–b);
console.log(b–);
*打印值：
10
12
9
9*
四、分别使用行内式、内嵌式、引入外部文件的方法造成网页弹窗，要求触发弹窗的 JavaScript 命令不止一种（alert、print、prompt）。
https://github.com/helenwami/security/blob/main/html%2Bjs/alert.html
https://github.com/helenwami/security/blob/main/html%2Bjs/print.html
https://github.com/helenwami/security/blob/main/html%2Bjs/prompt.html

五、安装 Docker 并练习以下基础命令、帮助命令、镜像命令和容器命令:
1.帮助命令
docker 命令 --help
```
minwang@minwang-vm-ubuntu:~$ docker images --help

Usage:  docker images [OPTIONS] [REPOSITORY[:TAG]]

List images

Aliases:
  docker image ls, docker image list, docker images

Options:
  -a, --all             Show all images (default hides intermediate images)
      --digests         Show digests
  -f, --filter filter   Filter output based on conditions provided
      --format string   Format output using a custom template:
                        'table':            Print output in table format with column headers (default)
                        'table TEMPLATE':   Print output in table format using the given Go template
                        'json':             Print in JSON format
                        'TEMPLATE':         Print output using the given Go template.
                        Refer to https://docs.docker.com/go/formatting/ for more information about formatting
                        output with templates
      --no-trunc        Don't truncate output
  -q, --quiet           Only show image IDs
  ```
2.镜像命令
docker images 列出所有镜像
```
minwang@minwang-vm-ubuntu:~$ docker images
REPOSITORY             TAG       IMAGE ID       CREATED         SIZE
redis                  latest    c4645622ca39   2 weeks ago     149MB
busybox                latest    fc9db2894f4e   3 weeks ago     4.04MB
kicbase/stable         v0.0.40   f52519afe5f6   4 weeks ago     1.1GB
mariadb                10        5fc7fccd2af9   5 weeks ago     386MB
registry               latest    daace2c8ce4c   2 months ago    23.8MB
127.0.0.1:5000/nginx   alpine    66bf2c914bf4   2 months ago    41MB
nginx                  alpine    66bf2c914bf4   2 months ago    41MB
alpine                 latest    5053b247d78b   2 months ago    7.66MB
nginx                  latest    2d21d843073b   2 months ago    192MB
hello-world            latest    b038788ddb22   3 months ago    9.14kB
wordpress              5         4e46e98a2e06   15 months ago   554MB
centos                 latest    e6a0117ec169   23 months ago   272MB
```
docker search 搜索镜像
```
minwang@minwang-vm-ubuntu:~$ docker search redis
NAME                                DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
redis                               Redis is an open source key-value store that…   12279     [OK]
redislabs/redisearch                Redis With the RedisSearch module pre-loaded…   57
redislabs/redisinsight              RedisInsight - The GUI for Redis                91
redislabs/rebloom                   A probablistic datatypes module for Redis       24                   [OK]
redislabs/redis                     Clustered in-memory database engine compatib…   38
redis/redis-stack-server            redis-stack-server installs a Redis server w…   51
redislabs/rejson                    RedisJSON - Enhanced JSON data type processi…   53
redis/redis-stack                   redis-stack installs a Redis server with add…   63
redislabs/redisgraph                A graph database module for Redis               26                   [OK]
redislabs/redismod                  An automated build of redismod - latest Redi…   41                   [OK]
redislabs/redistimeseries           A time series database module for Redis         12
redislabs/operator                                                                  7
redislabs/operator-internal         This repository contains pre-released versio…   1
redislabs/redis-py                                                                  5
redislabs/redis-webcli              A tiny Flask app to provide access to Redis …   3                    [OK]
redislabs/redisgears                An automated build of RedisGears                4
redislabs/k8s-controller-internal                                                   0
redislabs/memtier_benchmark         Docker image to run memtier_benchmark           0
redislabs/ng-redis-raft             Redis with redis raft module                    0
redislabs/k8s-controller                                                            2
redislabs/redisai                                                                   6
redislabs/olmtest                   Test artefact for OLM CSV                       1
bitnami/redis                       Bitnami Redis Docker Image                      263                  [OK]
redislabs/olm-bundle                                                                0
redislabs/redisml                   A Redis module that implements several machi…   3                    [OK]
```
docker pull 下载镜像
```
minwang@minwang-vm-ubuntu:~$ docker pull redis
Using default tag: latest
latest: Pulling from library/redis
Digest: sha256:b0bdc1a83caf43f9eb74afca0fcfd6f09bea38bb87f6add4a858f06ef4617538
Status: Image is up to date for redis:latest
docker.io/library/redis:latest
```

docker rmi 删除镜像
```
minwang@minwang-vm-ubuntu:~$ docker images
REPOSITORY             TAG       IMAGE ID       CREATED         SIZE
redis                  latest    c4645622ca39   2 weeks ago     149MB
busybox                latest    fc9db2894f4e   3 weeks ago     4.04MB
kicbase/stable         v0.0.40   f52519afe5f6   4 weeks ago     1.1GB
mariadb                10        5fc7fccd2af9   5 weeks ago     386MB
registry               latest    daace2c8ce4c   2 months ago    23.8MB
127.0.0.1:5000/nginx   alpine    66bf2c914bf4   2 months ago    41MB
nginx                  alpine    66bf2c914bf4   2 months ago    41MB
alpine                 latest    5053b247d78b   2 months ago    7.66MB
nginx                  latest    2d21d843073b   2 months ago    192MB
hello-world            latest    b038788ddb22   3 months ago    9.14kB
wordpress              5         4e46e98a2e06   15 months ago   554MB
centos                 latest    e6a0117ec169   23 months ago   272MB
minwang@minwang-vm-ubuntu:~$ docker rmi c4645622ca39
Untagged: redis:latest
Untagged: redis@sha256:b0bdc1a83caf43f9eb74afca0fcfd6f09bea38bb87f6add4a858f06ef4617538
Deleted: sha256:c4645622ca3919b60b2d3a377c438b9d5de65cf76a63ca4c025733909db8c9ef
Deleted: sha256:4a7888b96ee262e07da804ea0a913a5a917f742f4d79b8d0a8157155cac2a99b
Deleted: sha256:24c4ccb7d22c4db3b6e51c032db5311b7c6624fc19b1480b09640d6942f9077c
Deleted: sha256:1988a5e179afcfdb5ef94c549f864ba5678b1a25f40a4fe1b39220f708d5ca8d
Deleted: sha256:8bcf93136ceb16be9a45c8ec0202c57b420aacf43cc45c51a7d7186e2f6d3684
Deleted: sha256:e40c691c868030fe07f5edc14022cca9ddd279045e9f1851736cd41ac995b926
Deleted: sha256:8450f74cd36b8dee83cbb893350e167acb792b321fad0c2180abfd1ef0fcdf55
```
