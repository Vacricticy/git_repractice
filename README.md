1.查看 Git 的使用方法 ： git

2.把当前文件夹变为一个 git 仓库 创建 git 仓库：git init

3.查看当前仓库文件变化情况：git status

4.添加修改(追踪文件的修改)：git add （可使用 git add . 来添加当前仓库所有修改）

5.查看本次还没有追踪的更改：git diff（比较工作区与暂存区的区别）

6.回滚，撤销提交操作：git reset

7.向 Git 提交自己身份（name）：git config --global user.name "xxx"

8.向 Git 提交自己身份（email）：git config --global user.email "xxx@xx.com"

9.向 Git 提交内容：git commit -m “xx” （xx 为对提交的内容进行描述）

10.让 Git 不提交某些文件/忽略某些文件：创建文件 .gitignore 并在文件中添加文件名/文件夹名 即可 （若 git 已经开始追踪某些文件 则需要 11）

11.让 Git 不再追踪某个/某些文件：git rm --cached xx （xx 为文件名）

12.Git 添加分支：git branch xx （xx 为分支名）

13.Git 切换分支：git checkout xx （xx 为分支名）

14.合并分支：git merge xx（xx 为分支名）

15.列出本地分支：git brancjh

16.删除分支:git branch -d xx (xx 为分支名，-D 强制删除)

17.添加远程仓库：git remote add origin xxx （xxx 为远程地址）

18.设置本地分支追踪远程分支：git push --set-upstream

19.克隆仓库：git clone xxx（xxx 为远程地址）
