##分支说明：
>
  master分支不用理会
>  
  devcom分支为已经完成分支
>  
  dev分支为正在开发分支
>  
  gh-pages分支为案例展示分支

##使用说明

如果您是在新的电脑上来完成项目，您需要完成一下操作，才可以正常写项目， 我相信这对您来说没有任何难处，因为它很简单。

首先你需要安装一下软件：

nodejs [下载地址](https://nodejs.org/en/)

git [下载地址](http://git-scm.com/download/)

这2个软件的官网会自动判断您当前的系统给您下载对应的系统的安装文件。

安装完成之后，您需要先配置您的git环境，

##设置Git的user name和email

```
$ git config --global user.name "iuunhao"
$ git config --global user.email "html.5@foxmail.com"
```

这里的信息请您和您的其他电脑的信息保持一致，免费github没有成员项目，所以我只能通过提交人的邮箱或者姓名来确定是不是我们的团队成员来合并您提交的代码。


##生成SSH密钥过程
1.查看是否已经有了ssh密钥：cd ~/.ssh
如果没有密钥则不会有此文件夹，有则备份删除
如果是win的环境的话，查看您的用户文档里面的.ssh文件如果有，可以删除它重新生成密钥。

2.生存密钥：
$ ssh-keygen -t rsa -C “haiyan.xu.vip@gmail.com”
请和上面的邮箱保持一致。
在弹出的提示中按3个回车，密码为空。

如果您看到这些信息说明已经生成成功：

>Your identification has been saved in /home/tekkub/.ssh/id_rsa.
>
Your public key has been saved in /home/tekkub/.ssh/id_rsa.pub.
The key fingerprint is:
>
………………

最后得到了两个文件：`id_rsa`和`id_rsa.pub`
打开`id_rsa.pub`文件，将内容复制。
添加至您的github里面。

1.登陆github之后，点击您的头像，在菜单中选择`settings`选项。

2.选择左侧的`SSH keys`菜单，并点击右上角的`New SSH keys`按钮。

3.在下方的`Titile`里面输出一个标识符，便于区分您的公钥都在哪些电脑上使用过。（因为如果存在这个公钥，那么你的所有远程仓库上的文件，只要使用了这个电脑的人都可以对文件进行全面的操作，比较危险。如果是一次性使用的电脑，使用后，就在这里的列表里面删除这个`SSH keys`。）

4.在下面的`Key`里面粘贴您刚才复制出来的`id_rsa.pub `内容。然后点击`Add SSH key`，这个时候会让你输出密码，就是您的github登陆密码。
完成这些操作之后，就可以开工了。

您可以先在电脑上找个位置右键`git bash`，这是会打开一个命令行工具，直接执行以下命令，拿到我们最新的项目结构及其项目文件。

我相信您能做到这步，说明，您已经fock了原始项目。前提是您的仓库我原始仓库的内容是保持一致的。否则会出现冲突。

```
git clone https://github.com/iuunhao/WEDO.git:dev
```
命令完成之后您会拿到最新的原始仓库dev分支的内容。

您需要执行以下命令绑定远程仓库：

```
git remote add origin https://github.com/iuunhao/WEDO.git:dev
```

这个时候您就可以pull更新代码 push提交代码了。

如果您感觉您提交次数过多，您可以换另外一种方式来操作。

您`fock`了原始项目之后，您的仓库里面会有一份文件，

```
git clone https://github.com/您的github用户名/WEDO.git:dev
```
您您随时都可以提交你的代码到您的仓库，等您在一个周期内，做完了一定任务，你就可以提交至原始仓库了。

提交您的代码到原始仓库，需要先绑定远程原始仓库，

```
git remote add o https://github.com/iuunhao/WEDO.git
```

这个时候您的本地仓库里面有2个远程仓库，一个是您自己的远程仓库，和一个原始的远程仓库，如果您要推送您的代码到原始仓库，您做以下操作即可：

```
//先更新原始仓库的代码避免文件冲突
git pull o

//拿到远程仓库的代码后，如果没有冲突，可以直接提交，如果有冲突先解决冲突再做提交
//添加您本地的文件到本地的仓库中
git add .

//将您的本地文件加入git版本控制中
git commit -am "提交说明"

//提交您本地仓库的dev分支到原始仓库的dev分支中
git push o:dev dev
```


>如果您的网络情况不是很理想，我已将所有`plugins`上传至网盘，您可以直接下载然后正常使用它。

[下载地址](http://pan.baidu.com/s/1gdZoZQj)

将node_modules解压至根目录即可。

当然如果你网络情况够好，您可以执行以下操作，但在我看来下载压缩包是一个好的选择，有一些插件并不一定能正常安装。

首先您将根目录下的 `gulpfile.js`文件拷贝至您的项目根目录。

如： 您即将要做一个移动端的项目目录结构如果下：

    ├── FED                              - 跟目录
    │   ├── mobile                       - 移动项目
    │       ├── 2016                     - 项目年份
    │           ├── 20160305中国移动      - 项目名称(前面加日期)
    │               ├── css              - 自动输出css目录
    │               ├── dest             - 项目全部自动整合至dest目录
    │               ├── zip              - 自动压缩dest目录文件至zip中
    │               ├── gulpfile.js      - gulp配置文件
    │               ├── sass             - sass目录
    │               ├── js               - js目录
    │               ├── jade             - jade目录
    │               ├── images           - 图片目录
    │                   ├── icon         - sprite目录
    │                   ├── temp         - 临时图片目录
    │   ├── pc                       - 移动项目
    │       ├── 2016                     - 项目年份
    │           ├── 20160305中国移动      - 项目名称(前面加日期)
    │               ├── css              - 自动输出css目录
    │               ├── dest             - 项目全部自动整合至dest目录
    │               ├── zip              - 自动压缩dest目录文件至zip中
    │               ├── gulpfile.js      - gulp配置文件
    │               ├── sass             - sass目录
    │               ├── js               - js目录
    │               ├── jade             - jade目录
    │               ├── images           - 图片目录
    │                   ├── icon         - sprite目录
    │                   ├── temp         - 临时图片目录


在此目录先执行

```
npm install
```

来安装插件，如果您已经下载压缩包，那您可以忽略这步。

如果你使用jade可以忽略jade目录，`css`,`dest`,`zip`这三个文件不需要手动创建，您运行`gulp`,`gulp zip`命令的时候会自动创建。

开始项目之前在此目录执行

```
gulp
```

命令即可开始项目的编写。

完成项目后，您可以使用以下命令来`优化`,`压缩`,`打包`。

```
gulp minimg      //压缩图片
gulp zip         //打包文件
```


>注意： 如果您发现好的`plugins`，需要添加，请联系我，为了保证所有项目不会受到影响。





