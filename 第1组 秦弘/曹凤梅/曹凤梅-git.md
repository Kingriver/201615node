## git
安装brew在mac上
mac http://brew.sh
```
brew install git 
```
### 1.1 告诉git你是谁
```
git config --global user.name xxxxx
git config --global user.email xxxxx
git config --list
```
### 1.2 初始化git
```
git init
```

### 创建并进入目录 
```
mkdir gitTest && cd gitTest
```

### ls显示所有文件
```
ls -al 显示隐藏的
```

### 创建文件
```
touch index.txt
cat index.txt 查看内容
```

### 查看git状态
```
git status 
```

### 添加到暂存区
```
git add .
```

### 提交到历史库
```
git commit -m 'write hello world'
```

### 对比代码
工作区和暂存区
```
git diff
```
暂存区和历史区 
```
git diff --cached
```
工作区和历史区 
```
git diff master(分支名)
```

## 查看日志
```
git log 过多可以使用上下键查看，不想看可以q退出
```

## 查看所有日志
```
git reflog
```
## 回滚
```
git reset --hard 版本号
```
## vi编辑
```
vi index.txt
i 编辑模式
esc + :wq 保存并退出  强制退出q!
```


## 分支管理
- 查看分支
```
git branch 
```
- 创建分支
```
git branch <branchName>
```
- 切换分支
```
git checkout <branchName>
```
- 删除分支（不能自己删除自己）
```

git branch -D <branchName>
```
- 创建并切换(相当于将当前内容克隆一份)
```
git checkout -b <branchName>
```
- 在master上合并dev分支
```
git merge dev
```
- 产生冲突(手动解决提交新的版本)

## 创建仓库
- 创建空仓库，写一个仓库名
```
new repository
```

- 本地要建一个README.md .gitignore
```
echo '.idea' >> .gitignore
echo 'welcome' >> README.md
```

- 提交并关联仓库
```
git add .
git commit -m ''
git remote add origin 地址
git remote -v 查看所有关联
git remote rm origin 删除
```
- 推送到远程仓库上
```
git push origin master(可以推送其他分支) -u(upstream 下次提交不必再输入origin master)
```

## 发布静态页
- 发布的静态页必须在gh-pages分支
```
git checkout -b gh-pages
git add .
git commit -m 
git push origin gh-pages
```

## 讲师有一个仓库 
```
- 组长fork我的仓库
- 将信息 放到自己的文件夹下提交代码
- 推送到github上
- 发送pull request请求合并
```

## 组长给组员开通权限
```
- 组员clone最新代码：创建一个新目录，然后git clone 组长仓库地址
- 放入自己的文件提交：在新目录下创建一个自己的文件夹，写入自己需要交的东西。重新推到历史区git add .  git commit -m''。
- 拉取组长的仓库的最新代码 git pull origin master
- 推送到组长仓库git push origin master
```
- 再次推送

## 组长推送给老师
- 先拉取自己组的最新代码
```
git pull origin master
```
- 拉取老师的最新代码
```
git remote add teacher https://github.com/zhufengzhufeng/201615node.git
git pull teacher master
```
- 推送到自己的仓库上
```
git push origin master
```
- pull request