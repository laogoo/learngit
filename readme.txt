Git is a version control system.
Git is free software
mkdir learngit
cd learngit
pwd

git init
git add xxx
git commit -m "xxx"
git status
git diff xxx
git log
git reflog

git reset --hard head^
git reset --hard 12345

git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令

场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。

echo aa>test.txt

ssh-keygen -t rsa -C"601765302@qq.com"
git remote add origin git@github.com:laogoo/learngit.git
git push -u origin master

git clone克隆一个本地库：$ git clone git@github.com:michaelliao/gitskills.git


创建dev分支，然后切换到dev分支：
$ git checkout -b dev
Switched to a new branch 'dev'

git checkout命令加上-b参数表示创建并切换，相当于以下两条命令：
$ git branch dev
$ git checkout dev
Switched to branch 'dev'

用git branch命令查看当前分支：
$ git branch
* dev
  master

把dev分支的工作成果合并到master分支上：
$ git merge dev

删除dev分支了：
$ git branch -d dev

Git鼓励大量使用分支：

查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

pull：本地 <-- 远程
push：本地 --> 远程

本质上都是同步commit

如果你本地落后远程，必然要pull
如果你本地超前远程，必然要push

&simple