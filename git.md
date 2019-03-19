

# 使用

## 合并冲突

* 希望保留生产服务器上所做的改动,仅仅并入新配置项, 处理方法如下:
```bash
git stash
git pull
git stash pop
```

### git diff -w +文件名 来确认代码自动合并的情况
```
* 希望用代码库中的文件完全覆盖本地工作版本.
```bash
git reset --hard
git pull

# git reset是针对版本,如果想针对文件回退本地修改,使用
# git checkout HEAD file/to/restore
```

## 添加公钥后仍然需要用户名和密码
* 这种问题只出现在https方式clone
* 修改项目配置文件
```git
git clone https://github.com/Name/project.git
git clone git@github.com:Name/project.git
```
## 分支

### 刷新远程分支
```bash
git fetch origin
```

### 拉取远程分支内容

```bash
git checkout -t origin/2.0.0
```
# 设置

## 每个项目设置自己的用户名和邮箱

```bash
git config --list //查看当前设置
git config user.name xxxxxx
git config user.email wxxxxx@gmail.com
```

## log记录图形显示
编辑`~/.gitconfig`文件，加入：
```bash
[alias]
lg1 = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all
lg2 = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)' --all
lg = !"git lg1"
```

## git status中文显示的unicode
```bash
git config --global core.quotepath false
```

## git status 中没有颜色高亮
```bash
git config --global color.ui true
```
## 使用icdiff做对比

1. 添加一人脚本，内容为
   ```bash
   #!/bin/bash
   icdiff $2 $5
   ```
2. 修改`~/.gitconfig`
   ```bash
   [diff]
	   #使用icdiff来取代git内建的diff
		external = ~/project/git-icdiff.sh
   ```
