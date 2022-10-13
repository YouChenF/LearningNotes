### 1. 基本概念

仓库(Repository)：存放项目的代码，每个项目对应一个仓库，多个项目就有多个仓库。

收藏(Star)：收藏别人的项目，方便下次查看

复制克隆项目(Fork)：复制别人的项目，作为自己的一个项目(与原项目独立)

发起请求(Pull request)：fork别人的项目后，自己进行了修改，可以pull request，然后对方查看，如果同意后，可以合并你的修改到原仓库

关注(Watch)：如果Watch了某个项目，那么这个项目只要有更新就会第一时间收到关于这个项目的更新

事务卡片(Issue)：发现代码Bug，可以发起讨论

Github主页：左侧显示用户动态，右侧显示该用户的仓库

仓库主页：显示项目的信息

个人主页：显示个人的信息

### 2. git 常用命令

设置用户名：git config --global user.name 
设置用户邮箱：git config --global user.email 
初始化本地库：git init
查看仓库状态：git status
添加文件到暂存区：git add {文件名称}
删除暂存区的文件：git rm --cache {文化名称}
提交暂存区到仓库：git commit -m "信息" {文件名称}
查看日志信息：git reflog | git log
修改默认分支为main：git config --global init.defaultBranch main
关联远程仓库：git remote add origin git@github.com:lenve/test.git  （git remote add {shortname} {url}，指定一个简单的名字，以便将来引用。)
合并本地仓库和远程仓库：git pull --rebase origin main （本地和远程仓库两者代码文件不同步）
推送本地仓库到远程仓库：git push -u origin main

### 3. git常用命令解析

`git pull `：参考链接：https://www.yiibai.com/git/git_pull.html
> 意思是：取回远程主机某个分支的更新，再与本地的指定分支合并。
> 本质是：在默认模式下，`git pull`是`git fetch`后跟`git merge FETCH_HEAD`的缩写。
> 如果使用--rebase，那么它会运行git rebase 而不是 git merge。
   
   


### 4. git常见问题

**问题1：Git错误提示Integrate the remote changes...的解决方法**

背景：远程创建了一个仓库，并创建了readme.md文件，然后本地新建了一个仓库，并和远程仓库关联起来了，我想将本地仓库推送到远程仓库中，使用git push命令报上诉错误，**出错的原因是本地仓库和远程仓库不同步，无法推送。**

解决办法：git pull --rebase origin main
参考链接：https://blog.csdn.net/qq15577969/article/details/107618389

**问题2：解决Git中fatal: refusing to merge unrelated histories**

背景：将本地仓库先远程仓库推送时，产生上述问题，出错的原因是本地仓库和远程仓库不同步，已经pull，但是没有将本地仓库和远程仓库同步，即远程仓库有readme.md，但是本地仓库没有，通过pull也没有将readme.md拉取下来。

解决办法：git pull origin master --allow-unrelated-histories
参考链接：https://developer.aliyun.com/article/614459

**问题3：解决git status不能显示中文**

背景：git status查看有改动但未提交的文件时总只显示数字串，显示不出中文文件名，非常不方
便。
原因：在默认设置下，中文文件名在工作区状态输出，中文名不能正确显示，而是显示为八进制的字符编码。

解决办法：输入命令 git config --global core.quotepath false
参考链接：https://zhuanlan.zhihu.com/p/133706032#






