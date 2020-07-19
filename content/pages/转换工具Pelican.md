title: markdown转html的python工具
date: 2020-07-20
author: Your Name Here

GitHub 推荐的网站生成软件包是 Jekll，是使用 Ruby 编写的。因为我是 Python 的忠实粉丝，所以我更喜欢 Pelican，这是一个基于 Python 的博客平台，可与 GitHub 很好地协同工作。
Pelican 和 Jekll 都可以将 Markdown 或 reStructuredText 中编写的内容转换为 HTML 以生成静态网站，并且两个生成器都支持定制的主题。

## 安装 Pelican
```
$ pip install pelican ghp-import Markdown
```
## 配置pelican
如[github pages 创建](.\github_pages_创建.md)所说，内容和展示一般建议放在不同的分支。

初始化应该在内容分支上运行。
```
$ pelican-quickstart
Welcome to pelican-quickstart v3.7.1.

This script will help you create a new Pelican-based website.

Please answer the following questions so this script can generate the files
needed by Pelican.

> Where do you want to create your new web site? [.]  
> What will be the title of this web site? Super blog
> Who will be the author of this web site? username
> What will be the default language of this web site? [en]
> Do you want to specify a URL prefix? e.g., http://example.com   (Y/n) n
> Do you want to enable article pagination? (Y/n)
> How many articles per page do you want? [10]
> What is your time zone? [Europe/Paris] US/Central
> Do you want to generate a Fabfile/Makefile to automate generation and publishing? (Y/n) y
> Do you want an auto-reload & simpleHTTP script to assist with theme and site development? (Y/n) y
> Do you want to upload your website using FTP? (y/N) n
> Do you want to upload your website using SSH? (y/N) n
> Do you want to upload your website using Dropbox? (y/N) n
> Do you want to upload your website using S3? (y/N) n
> Do you want to upload your website using Rackspace Cloud Files? (y/N) n
> Do you want to upload your website using GitHub Pages? (y/N) y
> Is this your personal page (username.github.io)? (y/N) y
Done. Your new project is available at /Users/username/blog
```
你可以对每个问题都采用默认值，但除了以下这些问题：
* 网站标题，应该唯一且特殊
* 网站作者，可以是个人用户名或你的全名
* 时区，可能你不在巴黎
* 上传到 GitHub 页面，我们选择


参考：
[使用 Python 在 GitHub 上运行你的博客](https://zhuanlan.zhihu.com/p/122956498)
