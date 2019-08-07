#                   git笔记
---
+ git是分布式版本控制系统  
+ git是用c语言写的  
+ git需要配置用户名和邮箱  
  > git config --global user.name "Your Name"  
  > git config --global user.email "email@example.com"
+ git创建版本库并对版本库进行管理
  > 版本库可以简单理解为一个目录，在这个目录下所有文件的增删改查都被git管理起来了，每个文件的增删改查都是可以追踪历史记录的。  
  > 创建一个文件夹 mkdir foldername  
  > 将其变为git管理的版本库 git init  
  > 创建一个文件，并加入到版本库 git add filename.txt  
  > 添加完成后将其提交 git commit -m "提交的说明"  
  > 查看仓库的情况 git status  
  > 查看文件修改的情况 git diff  
  > 查看历史提交的情况 git log  
  > 版本回退 git reset --hard HEAD^  
  > HEAD^ 是上一个版本 HEAD^^是上上个版本，当然，也可以通过加commit版本号回退版本  
  > 查看你每一步的提交记录 git reflog  
  > 丢弃工作区的修改 git checkout -- filename.txt  
  > 暂存区的修改也是可以返回到工作区的， git reset -- filename.txt  
  > 要关联一个远程库，使用命令git remote add origin git@server-name:path/repo-name.git  
  > 关联后，使用命令git push -u origin master第一次推送master分支的所有内容  
  > 此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改  
  > 从github上clone项目命令： git clone git@github.com:YunLife/projectName

