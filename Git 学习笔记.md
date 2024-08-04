# Git 学习笔记

## 常见指令

![image-20240724144609710](C:\Users\泰来\AppData\Roaming\Typora\typora-user-images\image-20240724144609710.png)

##### git add

- git add 单个文件名|通配符	把工作区的文件添加到暂存区
  - git add . 	把当前目录下所有文件都添加到暂存区

##### git commit

- git commit -m"备注名" 	把暂存区的文件提交至仓库 

##### git log

- git log [option]	查看历史记录

- all 显示所有分支
- pretty=oneline将提交信息显示为一行
- abbrev-commit 使得输出的commitld更简短
- graph以图的形式显示

##### git status

- git status	查看当前工作区、暂存区状态

##### git reset

- git reset --hard commitID 版本切换到目标版本

##### git branch

- git branch 分支名 创建一个不存在的分支
  - git branch -b 分支名 创建分支并切换到该分支
- git branch -d 分支名 删除分支(需要检查)
  - git branch -D 分支名 强制删除(不需检查)

##### git merge

- git merge 分支名 把该分支合并至当前分支

##### git remote

- git remote 查看当前配置有哪些远程仓库
  - git remote -v 查看实际链接地址

##### git push

- git push [alias] [branch]  将你的 [branch] 分支推送成为 [alias] 远程仓库上的 [branch] 分支
  - git push [-f] [--set-upstream] [远端名称[本地分支名] [:远程分支名] ]
  - 名称相同可以只写本地分支
  - git push origin master

## 仓库使用流程

- git init      初始化
- git add     添加到暂存
- git commit -m"备注名"   提交
- git-log
  - git reset --hard commitID

- git remote add origin git地址    上传
- git push -u origin master