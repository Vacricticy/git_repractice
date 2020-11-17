1.查看 Git 的使用方法 ： git

2.把当前文件夹变为一个 git 仓库 创建 git 仓库：git init

3.查看当前仓库文件变化情况：git status





基本使用：

- git add .
- git  commit -m 'xxx'
- git push origin xxx 将本地分支的head推送到xxx分支







4.添加修改(追踪文件的修改)：git add （可使用 git add . 来添加当前仓库所有修改）

5.查看本次还没有追踪的更改：git diff（比较工作区与暂存区的区别）

6.回滚，撤销提交操作：git reset

7.设置本地仓库的签名（name）：git config --global user.name "xxx"

8.设置本地仓库的签名（email）：git config --global user.email "xxx@xx.com"

- 查看本地仓库的信息：git config --local -l

9.向 Git 提交内容：git commit -m “xx” （xx 为对提交的内容进行描述）

10.让 Git 不提交某些文件/忽略某些文件：创建文件 .gitignore 并在文件中添加文件名/文件夹名 即可 （若 git 已经开始追踪某些文件 则需要 11）

11.让 Git 不再追踪某个/某些文件：git rm --cached xx （xx 为文件名）



14.合并分支：git merge xx（xx 为分支名）



17.添加远程仓库：git remote add origin xxx （xxx 为远程地址）

18.设置本地分支追踪远程分支：git push --set-upstream

- 推送本地分支到远程
  - git push -u origin master
  - git push

19.克隆仓库：git clone xxx [rename]（xxx 为远程地址,rename 为重命名的本地仓库文件名）

20.拉取远程仓库最新的数据：git pull

21.如何解决合并冲突的问题：

- 比如你是 boss，然后你和组员修改了相同的内容，当你们某个人已经提交了代码后，后一个人再提交的时候就会存在冲突的情况。
- 此时可以将远程仓库 pull 至本地，此时远程仓库与本地仓库会自动合并
- 在命令行提示中会显示哪些文件存在冲突。
- 在这些文件中，包含了冲突的各个版本，你需要做的就是根修改这个文件，选择自己想要留下的东西，然后再 add commit push 就可以了





## git config   设置单个仓库或用户的配置：

```shell
# 告诉Git你是谁

git config --global user.name "John Smith"

git config --global user.email john@example.com

# 选择你喜欢的文本编辑器

git config --global core.editor vim

# 添加一些快捷方式(别名)

git config --global alias.st status

git config --global alias.co checkout

git config --global alias.br branch

git config --global alias.up rebase

git config --global alias.ci commit
```





## git status    查看仓库的状态：

```shell
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

#表示该文件已经添加到缓存中，等待commit提交
Changes to be committed:    
  (use "git reset HEAD <file>..." to unstage)

        new file:   index2.txt

#表示该文件还未被添加到缓存
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   index.html
        modified:   index2.txt

#表示该文件时新建的，还没有被跟踪。此时直接通过git add 可以将该文件进行跟踪，并添加到缓存中。所以执行git add xxx后该文件的状态会变为 changes to be committed
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        index3.txt
```





## git log    查看仓库的状态



```
git log
```

使用默认格式显示完整地项目历史。如果输出超过一屏，你可以用 `空格键` 来滚动，按 `q` 退出。

```
git log -n <limit>
```

用 `<limit>` 限制提交的数量。比如 `git log -n 3` 只会显示 3 个提交。

```
git log --oneline
```

将每个提交压缩到一行。当你需要查看项目历史的上层情况时这会很有用。

```
git log --stat
```

除了 `git log` 信息之外，包含哪些文件被更改了，以及每个文件相对的增删行数。

```
git log -p
```

显示代表每个提交的一堆信息。显示每个提交全部的差异（diff），这也是项目历史中最详细的视图。

```
git log --author="<pattern>"
```

搜索特定作者的提交。`<pattern>` 可以是字符串或正则表达式。

```
git log --grep="<pattern>"
```

搜索提交信息匹配特定 `<pattern>` 的提交。`<pattern>` 可以是字符串或正则表达式。

```
git log <since>..<until>
```

只显示发生在 `<since>` 和 `<until>` 之间的提交。两个参数可以是提交 ID、分支名、`HEAD` 或是任何一种引用。

```
git log <file>
```

只显示包含特定文件的提交。查找特定文件的历史这样做会很方便。

```
git log --graph --decorate --oneline
```

还有一些有用的选项。`--graph` 标记会绘制一幅字符组成的图形，左边是提交，右边是提交信息。`--decorate` 标记会加上提交所在的分支名称和标签。`--oneline` 标记将提交信息显示在同一行，一目了然。









分支相关：

- git branch xxx 创建xxx分支
- git checkout xxx 切换至xxx分支
- git checkout -b xxx 创建并切换至xxx分支
- git branch 列出本地的分支
- git branch -d xxx 删除本地的xxx分支 -D表示强制删除