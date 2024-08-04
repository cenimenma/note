### Git 学习笔记

##### 常见指令

![image-20240724144609710](C:\Users\泰来\AppData\Roaming\Typora\typora-user-images\image-20240724144609710.png)

- git add 单个文件名|通配符	把工作区的文件添加到暂存区
  - git add . 	把当前目录下所有文件都添加到暂存区

- git commit -m"备注名" 	把暂存区的文件提交至仓库 

- git log [option]	查看历史记录
  - all 显示所有分支
  - pretty=oneline将提交信息显示为一行
  - abbrev-commit 使得输出的commitld更简短
  - graph以图的形式显示

- git status	查看当前工作区、暂存区状态

- git reset --hard commitID 版本切换到目标版本