title: markdown转html的python工具
date: 2020-07-20
author: Your Name Here

GitHub 推荐的网站生成软件包是 Jekll，是使用 Ruby 编写的。因为我是 Python 的忠实粉丝，所以我更喜欢 Pelican，这是一个基于 Python 的博客平台，可与 GitHub 很好地协同工作。
Pelican 和 Jekll 都可以将 Markdown 或 reStructuredText 中编写的内容转换为 HTML 以生成静态网站，并且两个生成器都支持定制的主题。

## 安装 Pelican
```
$ pip install pelican ghp-import Markdown
```
## 创建库然后clone到本地
本文以 `https://GitHub.com/username/username.github.io`为例。username需要替换为自己的用户名。

## 创建一个分支content，并检出
`$ git checkout -b content`

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
回答完所有问题后，Pelican 会在当前目录中留下以下内容：
```
$ ls
Makefile      content/     develop_server.sh*
fabfile.py    output/      pelicanconf.py
publishconf.py
```
可以看到pelican自动创建了两个新目录。
## 将生成的文件提交到本地仓库中
## 在content目录下建立两个新的文件夹*pages*和*images*
文件名是pelican的约定，必须相同。
在pages下放置创建的网页markdown源文件。
## 生成
在output中生成html文件
```
$ pelican content -o output -s publishconf.py
```
## 导出
将output中的文件导出到master分支中
```
$ ghp-import -m "Generate Pelican site" --no-jekyll -b master output
```
## 将本地内容推送到github即可访问相关网页
```
$ git add content
$ git commit -m 'added a first post, a photo and an about page' $ git push origin content
```
## 访问
```
https://username.github.io
```
![图片测试1](green_ground.jpg)
![图片测试2][..\images\green_ground.jpg]
![图片测试3](..\images\green_ground.jpg)
![图片测试4](D:\workspace\github\zengjunfeng.github.io\output\images)

参考：
[使用 Python 在 GitHub 上运行你的博客](https://zhuanlan.zhihu.com/p/122956498)
