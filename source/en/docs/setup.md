title: 安装
---

安装 Xblog 只需几分钟时间，若您在安装过程中遇到问题或无法找到解决方式，请[提交问题](https://github.com/lufficc/Xblog/issues)，我会尽力解决您的问题。

### 安装前提

Xblog就是一个普通的基于laravel5.3的应用程序。所以你的电脑要拥有运行laravel应用程序的环境, 点击[这里](https://laravel.com/docs/5.3/installation)查看安装教程。

假设你已经拥有了必备的条件电脑中已经安装上述必备程序，那么恭喜您！接下来只需要使用 composer 即可完成 Xblog 的安装。
如果您的电脑中已经安装上述必备程序，那么恭喜您！接下来只需要使用 composer 即可完成 Xblog 的安装。

``` bash
$ composer require lufficc/xblog
```


有一些建议的可选的软件:
- Redis: Cache, Session, Queue 要用到, 这可以大大加速你的应用程序。

- Supervisor: 如果你用到了邮件提醒, 那么将使用Supervisor来开启队列发送邮件。你可以暂时忽略。

当然,你也可以不用做任何配置,默认是关闭缓存和邮件提醒的。

如果你做本地开发, 强烈建议使用官方的[Homestead](https://laravel.com/docs/5.3/homestead)进行开发, 它已经包括了Xblog的所有依赖软件。


### 安装 Redis

- Windows：下载并安装 [git](https://git-scm.com/download/win).
- Mac：使用 [Homebrew](http://mxcl.github.com/homebrew/) `brew install redis`
- Linux (Ubuntu, Debian)：`sudo apt-get install redis-server`

### 安装 Supervisor

- Linux: `sudo apt-get install supervisor`

### 注意, 如果你使用了[Homestead](https://laravel.com/docs/5.3/homestead)进行开发, 上述依赖已经存在, 不用安装。