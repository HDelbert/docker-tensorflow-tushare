# 通过Docker使用TuShare

这里有三个容器，都是为TuShare使用的。一个继承于tensorflow，方便使用tensorflow对数据进行学习；第二个是继承自jupyter/scipy-docker，里面有很多科学计算的python库；第三个是只有tushare的，简单容器。这些容器都是用ipython来操作的。

# 依赖

* [tensorflow](https://github.com/tensorflow/tensorflow)
* [tushare](https://github.com/waditu/tushare)
* [jupyter](https://github.com/jupyter/docker-stacks)

# 编译这个容器

克隆下这个仓库，然后使用下面命令编译

```bash
$ docker build --rm -t YOURNAME/tushare-tensorflow:VERSION .
```

如果你工作在一个使用代理的网络中，可以在Dockerfile第四行添加如下代码：

> ENV http_proxy "http://USERNAME:PASSWORD@your.proxy.com:port"  
> ENV https_proxy "https://USERNAME:PASSWORD@your.proxy.com:port"

# 运行这个容器

```bash
$ docker run --name tushare -d \
    --publish 8888:8888 \
    --volume /YOUR_PATH/notebooks:/notebooks \
    YOURNAME/tushare-tensorflow:VERSION

OR with Database container
$ docker run --name tushare_db -d \
    ****

$ docker run --name tushare -d \
    --publish 8888:8888 \
    --volume /home/YOURNAME/notebooks:/notebooks \
    --link tushare_db:database \
    YOURNAME/tushare-tensorflow:VERSION
```

# Contributing

If you find this image useful here's how you can help:

* Send a Pull Request with your awesome new features and bug fixes.
* Be a part of the community and help resolve Issues.
