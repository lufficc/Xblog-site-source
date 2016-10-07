title: 配置
---
您可以在 `.env` 中修改大部份的配置。

如果你已经将Xblog下载到本地,进入到目录:`cd xblog`, 更新依赖:
```
$ composer update
```
待所有依赖安装完毕, 进行配置。

## `.env`

下面是一些独有的配置, 其他配置和laravel一样。

参数 | 描述
--- | ---
`SITE_NAME` | 网站名称, 发邮件时用到
`EMAIL` | 当有人评论你的文章时的目的邮件地址, 覆盖管理员邮箱。可以忽略, 忽略时采用你注册时的邮箱。
`AVATAR` | 采用自带评论时或者用户注册的默认头像URL地址。
`QINIU_AK` | 七牛云存储的AccessKey, 建议申请, 否则图片保存到本地是个不小的开销。
`QINIU_SK` | 七牛云存储的SecretKey。
`QINIU_BUCKET` | 您的七牛BUCKET名字。
`QINIU_DEFAULT_DOMAIN` | 您的七牛域名,格式为http://*.*.*.*
`QINIU_HTTPS_DOMAIN` | 您自定义的七牛HTTPS域名, 和上者选其一, 格式为https://*.*.*/
`QINIU_CUSTOM_DOMAIN` | 自定义域名, 可以忽略。
`GITHUB_CLIENT_ID` | Github client_id, 如果你允许Github用户注册你的站点,请填写, 否则忽略。
`GITHUB_CLIENT_SECRET` | Github client_secret, 同上。
`GITHUB_REDIRECT` | Github redirect, 同上。
`ALGOLIA_APP_ID` | 如果你使用algolia的搜索服务, 请填写。
`ALGOLIA_SECRET` | 同上。
 `CACHE_DRIVER` | 默认为Redis, 建议为Redis。
 `SESSION_DRIVER` | 默认为Redis, 建议为Redis。
 `QUEUE_DRIVER` | 默认为Redis, 建议为Redis。
    

## 迁移

按需配置好你的`.env`文件之后， 运行迁移：
```
$ php artisan migrate
```
这会生成12个数据表:

1.  `users`   //用户表
2.  `posts`  // 文章表
3.  `categories`  分类表
4.  `tags`  //标签表
5.  `post_tag`  //文章，标签 多对多关系表
6.  `pages`  // 页面，比如我的about
7.  `files` //存储文件的key
8.  `comments`  //评论表
9.  `maps`   //存储键值对，比如网站的设置信息等
10.  `password_resets`   //Reset密码表
11.  `failed_jobs`   //失败队列表
12.  `notifications`   //通知表


只有在发送邮件和更新[algolia](https://www.algolia.com/)索引的时候用到， 如果你既不用邮提醒，也不用搜索功能， 请忽略。

## 设置网站

到目前为止， 你的网站已经可以运行， 先去注册你的账户，第一个用户（ID为1）将是管理员。

注册完毕进入后台， 进行你的网站设置, 下面列举可能让人疑惑的表单选项：
选项 | 描述
--- | ---
`跟踪ID` | 谷歌分析采用的ID
`Js` | 你的Js文件加速地址，你可以利用文件上功能将Js文件上传到七牛云，将链接复制填到这里。如果不填， 将采用本地文件。
`Css` | 同上。
`QINIU_AK` | 七牛云存储的AccessKey, 建议申请, 否则图片保存到本地是个不小的开销。
`QINIU_SK` | 七牛云存储的SecretKey。
`背景图片` | 网站的header背景图片url，也支持base64的图片数据。
`简介图片` | 网站侧栏个人信息的背景图片url，也支持base64的图片数据。

## 填充数据

如果是在本地环境， 可以用假数据填充让你的博客不那么空荡荡， 方便测试：
```
$ php artisan db:seed
```