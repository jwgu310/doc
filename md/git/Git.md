
# Git的使用

## 配置使用人的账号和邮箱

	git config --global user.name zhufengzhufeng
	git config --global user.email xxxxx
	git config --list 查看所有配置


mkdir 创建目录

## 初始化git

	git init

## 初始化文件

	echo hello > index.txt       覆盖写入
	echo hello word >> index.txt 写入
	cat index.txt  查看文本里的内容


> 一个大于号表示清空并写入 >> 表示 追加

## 删除文件rm

## 查看状态  git status

## 将文件加入到暂存区中

```
git add file
git add ./git add -A
```

## 提交commit

```
git commit -m"first"
```

## vi控制台
如果进入编辑模式可以i键进入插入模式

- i表示编辑
- 退出esc + :wq

## 查看版本库信息

	git log --oneline 查看版本库信息
	git reflog   查看未来的版本


## 比较代码差异
 
	git diff            比较工作区和暂存区的区别
	git diff master     比较工作区和版本库的区别
	git diff --cached   比较暂存区和版本库的区别


## 从暂存区删除本次的add

```
git reset HEAD <file>
```

> 取消本次的add

## 从缓存区 从历史区将代码覆盖掉工作区

```
		git checkout <file>
``` 

## 回到过去

```
git reset --hard commit_id/HEAD^^^^^^^/HEAD~6
```


## 分支

	查看所有分支git branch 
	创建分支git branch dev
	切换分支git checkout dev 
	创建并切换git checkout -b fixbug
	删除分支git branch -d dev
	合并分支git merge 分支名

> 在主干上拉取一条分支，在分支上进行开发，开发后，在主干上将代码进行合并，主干上目前没有人开发，
可以使用快转的方式，将我们的指针直接指向到分支的最新装态 fast-forward

## 在github上部署静态页

需要将特定的内容推送到github上的gh-pages分支上

- 创建一个gh-pages的分支
```
git checkout -b gh-pages
```

- 将代码commit 到这个分支上

```
git add .
git commit -m 'ok'
```

- 连接远程仓库和本地仓库

```
git remote add aaa 地址
```

- 将代码推送到远程仓库上

```
git push aaa gh-pages
```

##合并分支产生冲突

	git log --graph --oneline --decorate 查看

## 合并分支产生冲突

- 在主干的某个版本上进行分支开发，在分支上开发1.txt这个文件(drag)，在主干上也开发1.txt(limit),此时回到主干上合并时，会产生冲突，需要我们手动解决

## 从工作区中提交到历史区

```
git commit -a -m'drag'
```

## 解决冲突
去掉>>>>>> ========  <<<<<<< 保留需要的内容再次提交

## 合并
git rebase 变基
git cherry-pick 精选

## 显示结构

```
git log --graph --oneline --decorate
```

## 创建忽略文件

将项目提交到github上，需要在github上创建一个空的仓库

## 添加远程仓库的连接

```
git remote add 名字  地址
```

## 查看配置的所有配置的地址

```
git remote -v
```

## 删除地址

```
git remote rm 名字
```

## upstream

```
-u 下次提交或者拉取代码可以直接git push 或者git pull
```

    
