
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



  
  [参考链接](http://blog.jobbole.com/78960/)
