# MAC安装 RabbitMQ

### 1.用brew安装

`brew update`

`brew install rabbitmq`

### 2.设置环境变量

`export PATH=$PATH:/usr/local/opt/rabbitmq/sbin` 

### 3.启动rabbitmq

`rabbitmq-server`

![image-20200508155559187](/Users/mac/Library/Application Support/typora-user-images/image-20200508155559187.png)

后台启动用`rabbitmq-server -detached`

后台启动的关闭`rabbitmqctl stop`
