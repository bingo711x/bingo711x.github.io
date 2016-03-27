# Git使用
## 安装与配置
### 安装
Linux平台安装git（ubuntu）,或者更老一点的ubuntu系列Linux（git-core）
 
 ` sudo apt-get install git`

 ` sudo apt-get install git-core`

其他的Linux则使用源码安装

` ./configure --prefix = xxx`

` make`

` make install`

### 配置
git用户和对应email配置

` git config --global user.name "bingo"`

` git config --global user.email "xxx@xxx.com"`

## 初始化

* 创建文件夹，然后初始化
* 添加文件，并提交到本地版本库

` mkdir repo`

` cd repo`

` git init`

` git add Readme.txt 或者 . 或者 sort/ :把文件加入暂存区`

` git commit -m "wrote a readme file" :把暂存区内容提交到分支`

## 版本
用户可以具体查看有哪些地方有更该，然后再提交

` git status`

` git diff 查看哪里有更改`

如果有多个版本，需要回退的时候可以查看

` git log`

` git log --pretty=oneline`

回退

* HEAD^表示上一个版本
* HEAD^^表示上两个版本
* HEAD~100表示往前退100个版本

`git reset --hard HEAD^`

若想再回到新的版本，则要么记起之前版本号，要么从命令记录中查看
* `git reset --hard 3628164`
* `git reflog`

> **git add**指示把修改放入暂存区，只有commit以后才会放入版本库

`git checkout -- readme.txt :清除暂存区的内容****`
用版本库中 内容替换暂存区

`git reset HEAD readme.txt 也可以清除暂存区`

## 远程仓库
### Github建库然后与本地关联

`git remote add origin git@github.com:michaelliao/learngit.git`

`git push -u origin master 关联上并且推送上去`

以后每次推送就可以直接使用

`git push origin master`

### 克隆clone
`git clone git@github.com:michaelliao/gitskills.git`

## 分支管理
`git checkout -b dev`
等效与以下两条命令
* git branch dev 创建分支dev
* git checkout dev 转换到制定分支

`git branch 查看当前分支`

`git merge dev 合并制定分支到当前分支`

 `git branch -d dev 删除分支dev`
 
### 存在分歧
 
 `git merge feature1`
 
 `git status`
 
 手工解决冲突以后
 
`git add readme.txt`
 
`git commit -m "xxxx"`

`git log --graph` 
`--pretty=oneline --abbrev-commit`


 
 












