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
