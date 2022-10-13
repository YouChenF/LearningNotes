### 基本概念

仓库(Repository)：存放项目的代码，每个项目对应一个仓库，多个项目就有多个仓库。

收藏(Star)：收藏别人的项目，方便下次查看

复制克隆项目(Fork)：复制别人的项目，作为自己的一个项目(与原项目独立)

发起请求(Pull request)：fork别人的项目后，自己进行了修改，可以pull request，然后对方查看，如果同意后，可以合并你的修改到原仓库

关注(Watch)：如果Watch了某个项目，那么这个项目只要有更新就会第一时间收到关于这个项目的更新

事务卡片(Issue)：发现代码Bug，可以发起讨论

Github主页：左侧显示用户动态，右侧显示该用户的仓库

仓库主页：显示项目的信息

个人主页：显示个人的信息

### git 常用命令

设置用户名：git config --global user.name 
设置用户邮箱：git config --global user.email 
初始化本地库：git init
查看仓库状态：git status
添加文件到暂存区：git add {文件名称}
删除暂存区的文件：git rm --cache {文化名称}
提交暂存区到仓库：git commit -m "信息" {文件名称}
查看日志信息：git reflog | git log
修改默认分支为main：git config --global init.defaultBranch main

