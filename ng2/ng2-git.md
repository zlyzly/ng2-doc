### git命令 
```
    添加全部变更到缓存： 
    git add .

    添加指定文件的变更到缓存：
    git add 文件名

    提交缓存的变更到本地仓库：  
    git commit -m "代码提交的说明"  

    提交本地仓库的变更到远程仓库的mes分支：
    git push -u origin mes 

    提交自己项目并与主分支合并：
    查看所有分支，不在自己的分支，注意切换 
    git branch 

    如果当前分支不是自己的分支,变更当前工作分支到自己分支：切换到想去的分支：
    git checkout **

    查看所有源，初始origin， -v可以看到明细
    git remote -v 

    查看当前的状态，较上次的修改
    git status

    先添加到本地缓存中 "."添加所有修改过的文件，单独添加某一个，带上文件名
    git add .

    提交本地缓存到本地仓库，若是提交lssues，在注释中 fiexd #111:lssues的问题编号
    git commit -m "注释 fiexd #111"

    从本地仓库的添加到远程仓库的某一个源的分支：
    git push -u origin ***

    在gitlab中提出申请与主分支合并

    删除某一个源
    git remote remove  源名 

    新建分支
    比如你拉库的代码，本地就会有一个与原库对应的分支dev，在开发多个任务时，如果忘记新建一个分支去开发没有关系，只要本地的dev分支没有提交过，即使修改过，此时建分支，这个新的分支相当于copy了dev最初的版本，如果dev有提交过在建分支，新建的分支就是dev最新的版本

    切回到上次提交
    git reset --hard HEAD^  当前版本HEAD,上一个版本HEAD^,上上个版本HEAD^^
    git reset --hard 130f10a  或HEAD~100

    查看命令记录
    git reflog

    先提交到自己分支，保证是干净的，才能与主分支合并。
    git status 
    git add .
    git commit -m "dd"
    git push vosung zhangly 先保证自己的分支干净才能去拉新的代码
    git checkout  主分支
    git pull origin mes 拉下来(主分支)新的代码
    git checkout 自己分支 
    git merge mes  与新的代码合并
    git pull  查看有无冲突，修改后运行项目成功 
    git push 再次推到自己分支 
    请求合并 
```