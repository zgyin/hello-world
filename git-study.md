
先记录以后用Markdown语法来处理一下:  
git 安装完毕  
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



  
  [参考链接](http://blog.jobbole.com/78960/)
