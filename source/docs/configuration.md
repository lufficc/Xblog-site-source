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
    



## 网址

参数 | 描述 | 默认值
--- | --- | ---
`url` | 网址 |
`root` | 网站根目录 |
`permalink` | 文章的 [永久链接](permalinks.html) 格式 | `:year/:month/:day/:title/`
`permalink_default` | 永久链接中各部分的默认值 |

{% note info 网站存放在子目录 %}
如果您的网站存放在子目录中，例如 `http://yoursite.com/blog`，则请将您的 `url` 设为 `http://yoursite.com/blog` 并把 `root` 设为 `/blog/`。
{% endnote %}

## 目录

参数 | 描述 | 默认值
--- | --- | ---
`source_dir` | 资源文件夹，这个文件夹用来存放内容。 | `source`
`public_dir` | 公共文件夹，这个文件夹用于存放生成的站点文件。 | `public`
`tag_dir` | 标签文件夹 | `tags`
`archive_dir` | 归档文件夹 | `archives`
`category_dir` | 分类文件夹 | `categories`
`code_dir` | Include code 文件夹 | `downloads/code`
`i18n_dir` | 国际化（i18n）文件夹 | `:lang`
`skip_render` | 跳过指定文件的渲染，您可使用 [glob 表达式](https://github.com/isaacs/node-glob)来匹配路径。 |

## 文章

参数 | 描述 | 默认值
--- | --- | ---
`new_post_name` | 新文章的文件名称 | :title.md
`default_layout` | 预设布局 | post
`auto_spacing` | 在中文和英文之间加入空格 | false
`titlecase` | 把标题转换为 title case | false
`external_link` | 在新标签中打开链接 | true
`filename_case` | 把文件名称转换为 (1) 小写或 (2) 大写 | 0
`render_drafts` | 显示草稿 | false
`post_asset_folder` | 启动 [Asset 文件夹](asset-folders.html) | false
`relative_link` | 把链接改为与根目录的相对位址 | false
`future` | 显示未来的文章 | true
`highlight` | 代码块的设置 |

## 分类 & 标签

参数 | 描述 | 默认值
--- | --- | ---
`default_category` | 默认分类 | `uncategorized`
`category_map` | 分类别名 |
`tag_map` | 标签别名 |

## 日期 / 时间格式

Hexo 使用 [Moment.js](http://momentjs.com/) 来解析和显示时间。

参数 | 描述 | 默认值
--- | --- | ---
`date_format` | 日期格式 | `YYYY-MM-DD`
`time_format` | 时间格式 | `H:mm:ss`

## 分页

参数 | 描述 | 默认值
--- | --- | ---
`per_page` | 每页显示的文章量 (0 = 关闭分页功能) | `10`
`pagination_dir` | 分页目录 | `page`

## 扩展

参数 | 描述
--- | ---
`theme` | 当前主题名称。值为`false`时禁用主题
`deploy` | 部署部分的设置
