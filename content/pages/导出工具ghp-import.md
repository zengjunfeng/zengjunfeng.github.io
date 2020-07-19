title: 导出页面的工具
date: 2020-07-20
author: 郑州峰

使用ghp-import将重写gh-pages分支。使用前要确保该分支的数据已得到适当备份。这个工具假定gh-pages branch是100%导出的，因此，你不应该修改该分支的任何文件，否则在下次导出时会导致损失。

## 使用方法：

```
Usage: ghp-import [OPTIONS] DIRECTORY

Options:
  -n, --no-jekyll       Include a .nojekyll file in the branch.
  -c CNAME, --cname=CNAME
                        Write a CNAME file with the given CNAME.
  -m MESG, --message=MESG
                        The commit message to use on the target branch.
  -p, --push            Push the branch to origin/{branch} after committing.
  -f, --force           Force the push to the repository
  -r REMOTE, --remote=REMOTE
                        The name of the remote to push to. [origin]
  -b BRANCH, --branch=BRANCH
                        Name of the branch to write to. [gh-pages]
  -s, --shell           Use the shell when invoking Git. [False]
  -l, --follow-links    Follow symlinks when adding files. [False]
  -h, --help            show this help message and exit
```
举例：将 output 提交到 master 分支
```
$ ghp-import -m "Generate Pelican site" --no-jekyll -b master output
```

在你的库里，只需要运行 `ghp-import $DOCS_DIR` ，`$DOCS_DIR`是准备**built**的文档的路径。这个操作会在你的gh-pages分支做一次提交(commit)。如果指定 `-p` 选项，就会尝试将分支push到github。缺省情况下，相当于运行 `git push origin gh-pages`，你也可以用 `-r` flag来指定不同的remote。

你可以用 `-b`指定不同的分支。

一些windows用户可能需要通过shell来运行git命令，这可以通过指定 `-s`来实现。

## License
ghp-import is distributed under the Tumbolia Public License. See the LICENSE file for more information.


参考：
1. [包作者文档](https://github.com/davisp/ghp-import)
