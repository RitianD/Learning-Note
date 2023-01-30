1. git commit 提交
git commit --amend 做小修改
3. git branch 分支名 创建分支 
4. git checkout -b 分支名 切换到该分支
5. git merge 分支名 将该分支上的改动合并到当前所在分支
6. git rebase 分支名 
--interactive 可简写为-i git会打开一个UI界面并列出将要被复制到目标分支的备选提交记录，它还会显示提交记录的哈希值和提交说明
·可调整提交记录的顺序（通过鼠标拖放来完成）
·删除你不想要的提交（通过切换pick的状态来完成，关闭就意味着你不想要这个提交记录）
·合并提交。把多个提交记录合并成一个

rebase的优点：使你的提交树变得很干净，所有提交都在一条线上
rebase的缺点：修改了提交树的历史

1. git checkout 结点 产生HEAD指向该结点
2. git log 查看提交记录的哈希值
3. 相对引用：基于当前结点—— 
^向上移动一个提交记录；
~<num> 向上移动多个提交记录 如~3
9.移动分支：如 git branch -f main HEAD~3 (-f为强制移动)
10.撤销变更：
git reset :回退提交记录，所做的变更还在，但是处于未加入暂存区状态
git revert :创建新提交——引入的更改未撤销对当前结点的提交（对远程仓库无效）
11.git cherry-pick  <提交号>... 将一些提交复制到当前所在位置（HEAD)
12git tag <命名> <结点号> 如git tag v1 c1 将标签命名为V1，并明确让它指向提交记录C1，如果不指定提交记录，git会用HEAD所指向的位置
13.git describe 帮助你在提交历史中移动了多次以后找到方向
git describe <ref> ref可以是任何能被git识别成提交记录的引用，如果没有指定的话，git会以目前所检出的位置（HEAD）
输出结果是这样的：
<tag>_<numCommits>_g<hash>
tag表示的是离ref最近的标签，numCommits是表示这个ref与tag相差多少个提交记录，hash表示的是所给定的ref所表示的提交记录哈希值的前几位。
当ref提交记录上有某个标签时，则只输出标签名称
14.git bisect 查找产生BUG的提交记录的指令

查看HEAD指向：
cat .git/HEAD
git symbolic-ref HEAD (查看HEAD指向的引用)

快速合并：
fast-forward快速合并到main分支

远程仓库：
1.git clone
2.git fetch：从远程仓库获取数据
·从远程仓库下载本地仓库中缺失的提交记录
·更新远程分支指针（如o/main)
！但git fetch不会改变本地仓库的状态。不会更新你的main分支，也不会修改你磁盘上的文件。
3.git pull
git pull --rebase = fetch+rebase
4.git push

ps.远程分支命名规范：<remote name>/<branch name>

让任意分支跟踪o/main的两种办法：
1.git checkout -b totallyNotMain o/main 创建了一个名为totallyNotMain的分支，它跟踪远程分支o/main
2.git branch -u o/main foo 这样foo就会跟踪o/main了。如果当前就在foo分支上，还可以省略foo