1.进入目标文件\
cd /c/Users/Gavin/Desktop/gitLearn\
pwd 显示当前路径 \
2.初始化库\
git init\
3.把文件提交缓存区n
git add 文件名.后缀\
4.将缓存区提交到本地仓库\
git commit -m"这是备注"
如果不加-m，就会打开cmomit日志，手动编写内容\
5.查看git状态\
git status\
会显示新增，删除，进入缓存区的文件\
当status显示没有东西时，说明都提交到本地仓库了\
6.查看文件\
cat 文件名.后缀\
7.查看commit记录\
git log                     详细记录\
git log --pretty=oneline    单行显示简洁记录\
git reflog                  显示所有提交记录\
8.查看修改内容\
git diff HEAD --文件名.后缀\
\
\
9.回退修改\
git checkout -- 文件名.后缀  切换文件，这里切的是缓存区，即恢复到缓存区的样子\
git reset HEAD 文件名.后缀   回退文件到最新的本地版本,此处是恢复到本地库的样子\
10.回退版本\
git reset --hard HEAD 此处的HEAD是最新版本,HEAD即是头部指针\
git reset --hard HEAD~X 此处的X是回退几个版本，即将头部指针后退多少下\
git reset --hard 3ed32 后面的乱码是版本ID，复制目标版本ID前几位\
11.删除文件\
rm 文件名.后缀\     只是删除了文件，暂存区和库里还在记录\
git rm 文件名.后缀  暂存区记录文件删除操作\
\
\
12.创建本地SSH\
ssh-keygen -t rsa -C "咱的邮箱"\
13.记录Github远程库\
git remote add origin 远程库的SSH地址       记录远程库\
git remote rm origin                       删除远程库记录\
14.提交本地库到远端
git push -u origin main   -u可以将本地main分支与远端main分支关联,关联后就不需要-u\
\
\
15.分支操作\
git branch                   查看分支\
git branch 名称              创建分支\
git checkout 名称            切换分支\
git switch   名称  \
git checkout -b 名称         创建并切换\
git switch -c   名称     \
git merge 名称               合并目标分支\
git branch -d 名称           删除分支\   
16.分支查看\
git log --graph                                  查看分支log\
git log --graph --pretty=oneline --abbrev-commit 简洁分支\
17.非快速合并\
git merge --no-ff -m "commit描述" 被合并分支的名称  \
默认合并是fastforword，main指针直接指向目标分支节点，非快速是复制一个节点到自己前面\
18.保存当前暂存区\
git stash                   保存当前暂存区\
git stash pop               弹出暂存区\
git stash list              查看暂存区\
git stash apply stash@{0}   应用list中指定的暂存区\
git stash drop              丢弃暂存区，即应用后删除\
\
\
19.执行单个commit操作\
git cherry-pick commit的编号    对当前分支执行该操作,顺利情况会添加新的节点，不顺利时需要解决冲突\
\
\
20.强制删除分支\
git branch -D 分支名\

