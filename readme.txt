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

test
<<<<<<< HEAD
&simple
=======
creating a new branch is quick AND simple
>>>>>>> branch

git merge --no-ff -m "merge with no-ff"dev 

Git还提供了一个stash功能，可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作：
$ git stash

$ git stash list

一是用git stash apply恢复，但是恢复后，stash内容并不删除，你需要用git stash drop来删除；

另一种方式是用git stash pop，恢复的同时把stash内容也删了：

查看远程库的信息，用git remote -v

推送分支：$ git push origin master

多人协作的工作模式通常是这样：

首先，可以试图用git push origin branch-name推送自己的修改；

如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；

如果合并有冲突，则解决冲突，并在本地提交；

没有冲突或者解决掉冲突后，再用git push origin branch-name推送就能成功！

如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream branch-name origin/branch-name。

小结

查看远程库信息，使用git remote -v；

本地新建的分支如果不推送到远程，对其他人就是不可见的；

从本地推送分支，使用git push origin branch-name，如果推送失败，先用git pull抓取远程的新提交；

在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致；

建立本地分支和远程分支的关联，使用git branch --set-upstream branch-name origin/branch-name；

从远程抓取分支，使用git pull，如果有冲突，要先处理冲突。

