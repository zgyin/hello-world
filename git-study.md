
先记录以后用Markdown语法来处理一下:  
Git 安装完毕  
新建目录 `mddir gitTest` `cd gitTest`  
初始化gitTest项目 `git init` 这时候多了.git 目录(这个目录是Git来跟踪管理版本的)  
![Alt git dir] () 待上传  
把文件添加到_暂存区_里面去  
`git add readme.txt` `git commit readme.txt` 'git status' 三个命令分别是 将文件添加到暂存区 提交文件到仓库 查看仓库状态（看有没有文件没有提交或者是没有被跟踪到）
可以另外添加文件 在不add的时候用 `git stauts` 对比看一下
new file:   readme2.txt     modified:   readme.txt 一个未提交 一个有修改  git diff readme.txt 查看修改了什么  

查看日志 `git log` 版本回退 `git reset  –hard HEAD^` `git reset  –hard HEAD^~2`
  获取到版本号 `git reflog`
`git reset  –hard 6fcfc89` 恢复到6fcfc89 版本  
Git 查看分支 `git branch`  
Git 创建分支 `git branch name`  
Git 切换分支 `git checkout name`  
Git 创建并切换分支 `git checkout -b name`  
Git 合并分支到当前分支 一般合并到master 先切换到master下 `git branch master` 合并 `git merge name`  
    合并完成后可以删除分支 `git branch -d name `  
Git用<<<<<<<，=======，>>>>>>>标记出不同分支的内容，其中<<<HEAD是指主分支修改的内容，>>>>>fenzhi1 是指fenzhi1上修改的内容



记录笔记参考： [git快速了解](http://blog.jobbole.com/78960/)  
#### 新建项目名称   
到目录下 git init  把这个目录变成git可以管理的仓库 生成.git文件夹=>跟踪版本用
新建文件 再提交到本地仓库 git commit  
  eg: git commit -m '测试提交功能'  
查看状态 git status  
  eg:（modified a.txt  说明修改了还未提交）  
查看到底改了什么 git diff a.txt  
确保可以提交了 先提交修改 再提交文件 2步  
  git add  
  git commit

#### 回退 回退前先看历史 git log  
git log -pretty=online   //格式化输出  
回退 git reset -hard HEAD^   HEAD^^ HEAD 10 前是10次对应？？

#### 工作区 暂存区  
工作区：就是你在电脑上看到的目录 如果你新加的文件   
.git 不属于工作区 是版本库里面内容很多 最重要的是暂存区stage 还有git为我们自动创建的第一个分支master分支 以及指向master的指针HEAD  
git add 就是把文件添加到暂存区  
git commit 提交更改 把暂存区的所有内容提交到当前分支上

#### 撤销处理或丢去处理  
git checkout -- a.txt 丢弃你在工作区对a.txt的修改 这样有2种情况都丢掉 文件修改后还没有add到暂存区 已经丢进暂存区并又修改了的 就撤销到添加到暂存区后的状态


#### 本地创建好了仓库 如何同步到远程github  
创建仓库 (登录github上，然后在右上角找到“create a new repo”在Repository name填入testgit，其他保持默认设置，点击“Create repository”按钮，就成功地创建了一个新的Git仓库)  
仓库关联 本地仓库内容推送到github  
eg:git remote add origin https://github.com/zgyin/test.git  
   git push -u origin master 把本地master仓库推送到远程origin   –u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

#### 创建合并分支  
严格说来 HEAD不指向提交指向master master才真正指向提交 HEAD指向当前分支  
创建分支   
  git checkout -b dev 创建并切换分支 -b创建并切换  
查看当前分支  
  git branch ( 加*号显示当前 其余代表还有多少分支)  
只是创建分支不切换  
  git branch test  只是创建test分支 任然在master上面  
切换分支   
  git checkout master 切换到master分支  
如果在dev分支 开发完成 要合并到master分支 再去提交  
git merge dev 在master上合并dev分支的内容  Fast-forward  快进模式 也就是直接把master指向dev的当前提交，所以合并速度非常快。
分支删除 git branch -d dev


#### stash 把当前工作现场隐藏 的现场恢复再继续工作 (临时bug修复 这个要提交)  
  git stash （将当前的工作现场隐藏）  
  git status 查看状态 是干净的  
  git checkout issue404  创建issue404分支修复bug 合并 提交

#### 多人协作工作模式一般是这样的：  
首先，可以试图用git push origin branch-name推送自己的修改.  
如果推送失败，则因为远程分支比你的本地更新早，需要先用git pull试图合并。  
如果合并有冲突，则需要解决冲突，并在本地提交。再用git push origin branch-name推送。
