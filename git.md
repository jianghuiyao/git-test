# git 配置以及相关操作命令
## 配置git
	git config 命令
	git config --list 显示当前git的配置信息
	git config -e 配置当仓库的信息
	git config -e --global  针对系统上的所有仓库

## 设置提交代码时的用户信息
	git config --global user.name "xxx"
	git config --global user.email xxx@xxx.com
	如果去掉--global参数只对当前仓库有效

## 本地进行git的创建
1. 选择一个目录作为git的仓库，只需要用git init命令来初始化它或者指定一个目录作为git仓库，用git init newrepo

2. 初始化完成后，在目录下会出现一个.git的目录，存放所有的git需要的数据和资源。然后将当前目录下的几个文件加入版本控制库中。需要用git add命令告诉git开始对这些文件追踪然后用 git commit -m “初始化项目版本”。如果前面没有添加远程仓库，则需要添加远程仓库：如：git remote add origin git@github.com:xxx/xxx.git。最后通过git push 推送到github仓库。
```
命令参考如下：
	git add README.md #添加文件到本地仓库
	git commit -m "first commit" #提交到本地库并备注，此时变更仍在本地。
	git commit -a  ##自动更新变化的文件，a可以理解为auto
	git push  #将本地文件提交到Github库中。此时才更新了本地变更到github服务上
```
## 从GitHub仓库下载到本地
1. 还可以使用git clone 从现有git仓库中拷贝项目。 如：git clone repo
2. 如果需要克隆到指定目录。 如：git clone repo directory
3. 如果拷贝其他人的项目。如 git clone git://github.com/xxx/xxx.git 要定义新建项目的名称。可以在命令末尾指定新名字。

## 远程上进行改动的操作
1. 查看当前的远程库：
	git remote  #加上-v参数看，可以看到每个别名的实际链接地址
2. 提取远程仓库：
	git pull #从远程仓库下载新分支到你所在的分支，远端仓库提取数据并尝试合并到当前分支
3. 推送到远程仓库
	git push origin master
4. 删除远程仓库
	git remote rm [仓库名]

## 分支管理
	git branch #显示当前分支是master
	git branch xxx  #创建分支命名为new_bra
	git checkout xxx  #切换到新分支
	git add readme.txt
	git commit -m "added readme.txt"
	git push origin xxx  ##把分支提交到远程服务器，只是把分支结构和内容提交到远程，并没有发生和主干的合并行为。

## 合并分支
	git checkout master  #切换到新主干
	git merge xxx  ##把分支合并到主干
	git branch #显示当前分支是master
	git push origin master #此时主干中也合并了xxx的代码

### 其他命令
	git remote update 别名 --prune  #更新远程分支列表
	git branch -a  #查看所有分支
	git push 别名 --delete 分支名  #删除远程分支
	git branch -d 分支名  #删除本地分支



