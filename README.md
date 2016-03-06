#WEIDO(此项目仅供个人使用)
>如果您的网络情况不是很理想，我已将所有`plugins`上传至网盘，您可以直接下载然后正常使用它。

[下载地址](http://pan.baidu.com/disk/home?fr=ibaidu#list/path=%2FWEIDO)

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




