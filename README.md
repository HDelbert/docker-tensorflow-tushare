# 通过Docker使用TuShare

这个容器继承自google的b.gcr.io/tensorflow/tensorflow，方便使用tensorflow来对股票数据做操作。

# 依赖

* [tensorflow](https://github.com/tensorflow/tensorflow)
* [tushare](https://github.com/waditu/tushare)

# 编译这个容器

克隆下这个仓库，然后使用下面命令编译

```bash
$ docker build --rm -t YOURNAME/tushare-tensorflow:VERSION .
```

如果你工作在一个使用代理的网络中，可以在Dockerfile第四行添加如下代码：

> ENV http_proxy "http://USERNAME:PASSWORD@your.proxy.com:port"  
ENV https_proxy "https://USERNAME:PASSWORD@your.proxy.com:port"

# 运行这个容器

```bash
$ docker run --name tushare -p 8888:8888 -d YOURNAME/tushare-tensorflow:VERSION
```

# Contributing

If you find this image useful here's how you can help:

   * Send a Pull Request with your awesome new features and bug fixes.
   * Be a part of the community and help resolve Issues.
