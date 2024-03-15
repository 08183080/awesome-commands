# awesome-commands
 操作系统/大语言模型上最常用的100条命令
# Windows
## PS和cmd命令之间的关系
```
在 PowerShell 中，可以使用大部分命令提示符（cmd）中的命令，但并不是所有的命令都能在 PowerShell 中完全等效地使用。例如，一些 cmd 中的命令可能有不同的语法或行为，或者在 PowerShell 中可能不存在直接的等效命令。
```
## PS command
## env varibales
- [x] $env:, **临时性设置环境变量, 注意cmd中的set命令丧失作用, 必须用$env:**
- [x] 在windows上搜索settings, 再搜搜env就可以编辑设置http_proxy, https_proxy这样的环境变量, restart生效
### text processsing
- [x] Select-String, 类似于Unix中的grep,功能>>findstr
- [x] findstr, 单纯的文本查找
## cmd commands
### single command
- [x] help, 提供windows上指令帮助
- [x] set, 设置当前的环境变量, 临时性
- [x] setx, 永久性设置环境变量
```
setx PATH "C:\Your\Path\Here;%PATH%"
注意, 添加过来的是目录路径, 譬如exe所在的目录而不是exe本身
``` 
- [x] ipconfig, 查看网络ip和dns的信息   
- [x] echo, 回声
- [x] cls, 清空当前cmd屏幕信息
- [x] ping, ip层的命令
- [x] netstat, 显示连接的TCP连接数, 计算机侦听的端口, 以太网统计信息 
- [x] nslokup, 查询域名系统(DNS)
- [x] tracert, 路由追踪
![Alt text](image.png)
- [x] wsl, windows上的linux子系统
```
wsl --list --all
wsl --unregister Ubuntu
```
- [x] ping: 主要用于测试网络连接的可用性, 但是公司内网可能ping不通外面网站的
- [x] wget: 主要用于从web服务器下载文件, 支持多种协议和递归下载以及断点续传
- [x] netstat, 查看端口
 - [x] netstat -aon|findstr "xxxx": 查看端口xxxx有没有被占用
- [x] findstr
- [x] dir, linux上的dir
- [x] clip, 将内容剪切到剪切板上. dir | clip组合使用
###  combine commands
#### console所有日志保存
```
pyinstaller run.spec > run.log 2>&1
```
根据run.spec导出exe的过程中, 将错误信息(2)也一起保存, 保存到run.log文件中
用powershell一条耕好用的命令则是:
```
pyinstllaer run.spec | tee run.log
```
powershell很power的
# Linux
```
Unix
    Linux
    WSL
```

- [x] man, manual, man xxx查看xxx命令
- [x] apt
```
apt-get update # 安装依赖更新
```
- [x] ifconfig, 查网络网卡ip,dns服务器,默认路由等
- [x] tcpdump, 网络监听抓包  
- [x] ps, 查看进程, process status, ps aux可以查看所有用户的所有进程
- [x] top, top可以实时展示当前进程状态
- [x] date +%s, 用于获取当前时间的Unix时间戳（Unix timestamp）的命令, Unix时间戳是指从格林威治时间1970年1月1日00:00:00（UTC）到当前时间的总秒数
# Chatgpt
here are some awesome chatgpt prompts.\
chatgpt必须在国外的ip, 你可以让它act as...(角色扮演)\
chatgpt简直是互联网上内容的化身呀...
- [x] prompt生成器:
```
I want you to act as a prompt generator. Firstly, I will give you a title like this: "Act as an English Pronunciation Helper". Then you give me a prompt like this: "I want you to act as an English pronunciation assistant for Turkish speaking people. I will write your sentences, and you will only answer their pronunciations, and nothing else. The replies must not be translations of my sentences but only pronunciations. Pronunciations should use Turkish Latin letters for phonetics. Do not write explanations on replies. My first sentence is "how the weather is in Istanbul?"." (You should adapt the sample prompt according to the title I gave. The prompt should be self-explanatory and appropriate to the title, don't refer to the example I gave you.). My first title is "Act as a Code Review Helper" (Give me prompt only)
```
## 可用的gpt源
- [x] gtp3.5, https://poe.com/
# Git
- [ ] git add
  - [ ] git add . 将当前所有的代码修改加入暂存区 
- [ ] git commit
  - [ ] git commit -m "xxx": 提交commit, messgae是"xxx" 
  - [ ] git commit --amend: 覆盖上次的pr, 保证一次pr解决一次问题, 具有唯一的一次commit 
- [ ] git stash
 - [ ] 本地修改暂时保留 
- [ ] git pull
  - [ ] a combination of git fetch + git merge
  - [ ] git pull --rebase: git pull --rebase 会将你的本地提交应用在对应分支的远程提交之上，而不是创建一个合并提交
  - [ ] git checkout
    - [ ] git checkout -b xxx: 创建分支xxx 
    - [ ] git checkout -b xxx origin/xxx
      - [ ] 本地创建分支xxx, 该分支追踪远程origin的分支xxx
 - [ ] git reset
   - [ ] 版本回退
   - [ ] git reset --hard
    - [ ] git reset --hard <commit-hash>
    - [ ] The **git reset --hard HEAD** command would discard all uncommitted changes even if you’ve added them to the staging area.
    - [ ] https://www.freecodecamp.org/news/git-reset-hard-how-to-reset-to-head-in-git/
 - [ ] git status
   - [ ] 查看分支状态
 - [ ] git branch
   - [ ] git branch 查看本地所有分支
   - [ ] git branch -d删除, -D强烈删除
 - [ ] git push
   - [ ] git push origin xxx: 将本地的分支push到远程上去
 - [ ] git log
   - [ ] For clarity, run git log --oneline to show your commit history
  # pip
  - [ ] pip list
  - [ ] pip install xxx
    - [ ] pip install --proxy=http://xxx.yyy.zzz:ddd (公司内部代理)【公司内网梯子代理pip】
    - [ ] pip install -i http://pypi.douban.com/simple/ （豆瓣源）【国内python源代理】
    - [ ] pip install xxx==a.b.c 【指定python版本号下载|有些时候得降低版本】
  # Notepad++ use
  - [ ] Ctrl+K: 默认是注释键
# Ideas
## 0,1,2
- [x] 在计算机编程中，0、1、2通常代表的是文件描述符。在Unix和类Unix系统中，0、1、2分别代表标准输入、标准输出和标准错误。0代表的是标准输入（stdin），它通常用于从键盘或其他程序获取输入
## 如何在ps中检查http_proxy和https_proxy设置成功
- [x] ping: 公司内网是ping不通的, 在ip层是没有代理的
- [x] wget: 我上次设置失败之后wget返回的状态码仍然是200, 也还是不行
- [ ] git: 尝试git clone一个很simple的repo能拉下来就ok （前提是没设置啥代理）
# Operations
- [x] 在windows上搜索settings, 再搜搜env就可以编辑设置http_proxy, https_proxy这样的环境变量, restart生效
- [x] 在windows上搜索settings, 再搜索startup就可以设置/关闭开机自启软件
 - [x] win+r, 输入 shell:startup 进入C:\Users\your_name\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup设置开启自启软件
- [x] win+r, 输入 msinfo32, 查看system information: OS, processor, bios, memory...
