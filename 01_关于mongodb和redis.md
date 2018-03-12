# mongoDB和redis

## mongodb的安装和配置的一些注意事项

网络爬虫总会爬取到json或者类似的结构化数据，利用Nosql技术可以更高效的存储

一些基础的mongo配置记录：

OS: windows 10  
mongo version: 3.6  
(**注意，不要将mongo装在Program Files下，因为这个文件名有空格，命令行会识别错误**)

1. 官网下载安装后，需要在安装目录下
新建：data/db 文件夹 以用来存储数据文件
2. 由于安装过程没有添加进环境变量的选项
所以需要在C:\MongoDB\Server\3.6\bin 目录下启动mongod
3. 执行如下命令将db路径设置好
mongod --dbpath C:\MongoDB\Server\3.6\data\db

到这里为止，在bin目录下命令行启动mongo,可以打开mongo命令行交互

下面将mongo配置成系统服务：

1. 管理员模式启动CMD，进入C:\MongoDB\Server\3.6\bin 目录下

2. 在C:\MongoDB\Server\3.6\data\db 目录下新建logs文件夹，并在其中新建mongo.log文件

3. 回到CMD，执行此命令： mongod --bind_ip 0.0.0.0 --logpath C:\MongoDB\Server\3.6\data\logs\mongo.log --logappend --dbpath C:\MongoDB\Server\3.6\data\db --port 27017 --serviceName "MongoDB" --serviceDisplayName "MongoDB" --install (**注意，不要将mongo装在Program Files下，因为这个文件名有空格，命令行会识别错误**)

4. 此时查看计算机管理中的服务，就可以看到MongoDB已经作为系统服务运行了

推荐的GUI　robomongo

## redis的安装和配置的一些注意事项

正常下载安装，redis版本众多，我下的是菜鸟教程提供的

安装GUI，推荐使用RedisDesktopManager(github找)