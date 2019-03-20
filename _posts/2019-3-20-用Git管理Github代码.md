---
layout:     post
title:      用Git和Github管理项目代码
subtitle:   让版本控制更优雅
date:       2019-03-20
author:     Jericho
header-img: img/post-bg-ios9-web.jpg
catalog: false
tags:
    - Git
    - Github
---
## Git关联Github
#### 1. 创建github账户
#### 2. 下载并安装git
#### 3. 本地生成公钥和私钥
git执行 `ssh-keygen -t rsa -C"你的邮箱"` ，出现如图输出即成功，在C://Users/用户名  里面找到.ssh文件夹，里面已经生成了两个文件 id_rsa 和 id_rsa.pub，分别是私钥和公钥。
![git生成公私钥](/img/article-pic/20-52-14.jpg)

#### 4. 关联github
回到github，点击右上角头像的setting，如图点击 "New SSH key" 
![](/img/article-pic/21-02-36.jpg)

将本地公钥全部内容粘贴到key里面，Title取一个合适的名字即可
![](/img/article-pic/21-04-54.jpg)

#### 5. 测试
在git bash中执行 `ssh -T git@github.com` ，然后输入 yes ，输出下图内容即关联成功。
![测试](/img/article-pic/21-08-15.jpg)

## 新增or修改内容
用到三个git命令，分别是`git add .`, `git commit -m "描述"`, `git push -u origin master`

>注：首次提交需要先输入身份信息
    
    git config --global user.emali "github注册邮箱"
    
    git config --global user.name "github用户名"