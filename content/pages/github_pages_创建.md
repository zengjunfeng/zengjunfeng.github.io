title: github pages 基本设置
date: 2020-07-20
author: 郑州峰

# github pages 基本设置
## 注册
进入 [github](https://github.com)，注册一个账户。
## 创建一个库（repository）
github支持两种静态网站。
### 1. 库名为 github.io （依据参考资料，尚未测试）
使用该库名，访问链接问 username.github.io/index.html
github将使用master作为网站的内容。
### 2. 其他名字的库
库创建好之后，点击右上角setting，然后找到“github pages”设置，在"update site"条目下，选择"Launch automatic page generator"按钮，将会弹出一些引导页面，点击确认即可自动创建index.html（后续可更改）。并自动创建gh-pages branch。index.html文件就放在此分支中。
访问链接为 username.github.io/库名/index.html
### 建议
将原始的md文件与展示的html文件，放到不同的分支。
## 使用github客户端或者git工具将库克隆(clone)到本地。
将网页文件上传到库中即可访问。
可以先clone到本地，更改后在push到github，会比较方便。
## 有一些工具支持
github 推荐的工具是 JekyII。
