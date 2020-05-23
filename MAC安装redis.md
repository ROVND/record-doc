# MAC安装redis

### 一 、安装命令

`brew install redis`

注意 不能用cask的

### 二、常用命令

### 1.brew启动redis

`brew services start redis`

提示内容

==> **Successfully started `redis` (label: homebrew.mxcl.redis)**

### 2.brew停止redis

`brew services stop redis`

Stopping `redis`... (might take a while)

==> **Successfully stopped `redis` (label: homebrew.mxcl.redis)**

### 3.使用配置文件启动redis-server

`redis-server /usr/local/etc/redis.conf`

启动界面

![image-20200507143618103](/Users/mac/Library/Application Support/typora-user-images/image-20200507143618103.png)z

这种启动方式 如果想关闭不仅需要关闭`终端`还需要执行`redis-cli shutdown`才能彻底关闭，要不下一次这么启动会报`127.0.0.1:6379: bind: Address already in use`

### 5.其他指令

查询redis进程`ps -ef | grep -i redis`

重启redis服务 `brew services restart redis`

打开图形化界面`redis-cli`

开机启动redis命令`ln -sfv /usr/local/opt/redis/*.plist ~/Library/LaunchAgents`

停止redis服务`redis-cli shutdown`

redis配置文件位置`/usr/local/etc/redis.conf`

卸载redis`brew uninstall redis rm ~/Library/LaunchAgents/homebrew.mxcl.redis.plist`

允许远程访问`vim /usr/local/etc/redis.conf`注释bind，默认情况下 redis不允许远程访问，只允许本机访问。redis增加了protected-mode，在这个模式下，即使注释掉了bind 127.0.0.1，再访问redisd时候还是报错，需要把protected-mode yes改为protected-mode no

