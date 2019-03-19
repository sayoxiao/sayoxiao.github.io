# 快捷链接
[Tmux快捷键列表](https://gist.github.com/ryerh/14b7c24dfd623ef8edc7)

[乌云文章列表](https://wooyun.js.org/)

[FRP设置例子](https://www.xyzbeta.com/460)

# Golang

## 交差编译
在一个环境下，编译出其它系统上可用的二进制文件
```bash
# 如果你想在Windows 32位系统下运行
➜  ~CGO_ENABLED=0 GOOS=windows GOARCH=386 go build test.go

# 如果你想在Windows 64位系统下运行
➜  ~CGO_ENABLED=0 GOOS=windows GOARCH=amd64 go build test.go

# 如果你想在OS X 32位系统下运行
➜  ~CGO_ENABLED=0 GOOS=darwin GOARCH=386 go build test.go

# 如果你想在OS X 64位系统下运行
➜  ~CGO_ENABLED=0 GOOS=darwin GOARCH=amd64 go build test.go

# 如果你想在Linux 32位系统下运行
➜  ~CGO_ENABLED=0 GOOS=linux GOARCH=386 go build test.go

# 如果你想在Linux 64位系统下运行
➜  ~CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build test.go
```

# wls

## 开机启动，并执行脚本

1 创建`wsl-ubuntu-init.vbs`脚本
```vbs
# win10中创建vbs脚本
Set ws = CreateObject("Wscript.Shell")
ws.run "bash -c 'sh /home/wangc/init.sh'",vbhide
```

2 在子系统中创建`init.sh`脚本
```bash
# 子系统中创建开机启动脚本
#!/bin/sh

sudo service ssh start
sudo service nginx start

$SHELL
```
3 vbs脚本添加到开机启动中

 * `win+r` + `shell:startup`





# python

## [打包为exe程序](https://www.zhihu.com/question/281858271/answer/611320245)
```python
#建立虚拟环境
pipenv install
#进入虚拟环境（上一步可省略,因为没有虚拟环境的话会自动建立一个）
pipenv shell
#安装模块
pip install requests pyquery pysimplegui fake_useragent
#打包的模块也要安装
pip install pyinstaller
#开始打包
pyinstaller -Fw E:\test\url_crawler.py

```
