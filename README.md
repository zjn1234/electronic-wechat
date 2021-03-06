<img src="assets/icon.png" alt="logo" height="120" align="right" />

# Electronic WeChat

[![Gitter](https://badges.gitter.im/geeeeeeeeek/electronic-wechat.svg)](https://gitter.im/geeeeeeeeek/electronic-wechat?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=body_badge)  [![Build Status](https://travis-ci.org/geeeeeeeeek/electronic-wechat.svg?branch=master)](https://travis-ci.org/geeeeeeeeek/electronic-wechat)  [![Build Status](https://img.shields.io/badge/README-切换语言-yellow.svg)](README_en.md)

**Mac OS X 和 Linux 下更好用的微信客户端. 更多功能, 更少bug. 使用[Electron](https://github.com/atom/electron)构建.**

## 该分支针对使用Dock的ubuntu进行改造

### 测试环境 ubuntu 18.04 gnome 3.28.1

#### 改造记录如下

> 1、更新所有依赖到最新版本(180511),其中Electronic@2.0.0

> 2、主窗体关闭按钮改为直接退出程序，不再是隐藏窗体

> 3、取消多实例检查，托管图标能正常使用了(偶然不能出来，感觉是Gnome的问题，关掉再开就好了。。)

> 4、修复菜单栏不能正常显示的BUG(通过ALT唤出)

> 5、删除偏好设置中是否使用多实例的设置选项(多实例可以通过右键dock图标新建窗口实现)

> ~~6、检查更新选项不再调用更新脚本，而是打开浏览器到Github发布页~~

> 7、添加全局快捷键CommandOrControl+Alt+W 显示微信

> 8、点击消息通知会打开微信(可以到设置页面关闭此功能)

> 9、修复设置页面不知为什么addEventListener不生效导致设置页形同虚设的bug

> 10、通过点击桌面的通知进入微信，现在可以直接自动打开对话框啦！

> 11、优化多语言的实现方式，系统托盘的菜单汉化以及添加偏好的选项

> 12、修复了当对方昵称或备注中有emoji时不能定位到该聊天框的bug

> 13、炫酷无边框，鼠标移到左上角显示菜单按钮(审美设计有点菜，等一个设计师)，设置页可以选择是否无边框(感谢[@waffiet-张](http://www.iconfont.cn/user/detail?spm=a313x.7781069.0.d214f71f6&uid=4435557)和[@竹尔](http://www.iconfont.cn/user/detail?spm=a313x.7781069.0.d214f71f6&uid=51853)的漂亮图标！！)

> 14、托盘菜单栏加上漂亮的icon

--- v2.0.5 ---

> 15、更改播放视频的背景色，解决打开视频后关闭按钮看不见的问题

> 16、加快了5倍左上角菜单的出现速度(0.5s → 0.1s)

--- v2.0.6 ---

<br>
<br>
<br>

#### 已知BUG

> 消息框右键的复制是是失效的

> 提示更新的弹框不能显示微信图标

> 播放视频的时候不能暂停

> 无法显示表情商店的表情（这是微信api的问题了，基本无解）

--- v2.0.6 ---

<br>
<br>
<br>

#### 新增的BUG QAQ

> ~~只能使用sudo进行调试，调试的时候不能显示消息通知~~

> 偏好设置窗口现在不能自由放大与缩小

> 消息通知不能显示对方头像(暂时用微信icon代替)

> 当聊天列表中有两个除去颜文字完全相同的昵称或者备注，并且其中一个是置顶的，那么点击消息通知打开微信会打开置顶的这个对话框，不管这个对话框是否有新消息

-- -v2.0.5 ---

> ~~点击通知进入微信时，不会自动从阅读或通讯录跳转至聊天界面~~

> ~~若干地方无法点击~~

--- v2.0.6 ---

<br>
<br>
<br>

#### [下载构建好的应用](https://github.com/kooritea/electronic-wechat/releases)

以下是原文



**Important:** 如果你希望在自己的电脑上构建 Electronic WeChat，请使用 [production branch](https://github.com/geeeeeeeeek/electronic-wechat/tree/production)，master branch 包含正在开发的部分，并且不能保证是稳定的版本——尽管 production 版本也有bug ：D

![qq20160428-0 2x](https://cloud.githubusercontent.com/assets/7262715/14876747/ff691ade-0d49-11e6-8435-cb1fac91b3c2.png)

## 应用特性 ([更新日志](CHANGELOG.md))

-  **来自网页版微信的更现代的界面和更丰富的功能**
-  **阻止消息撤回**
-  **显示表情贴纸** [[?]](https://github.com/geeeeeeeeek/electronic-wechat/issues/2)
-  公众号文章支持一键分享到微博、QQ 空间、Facebook、Twitter、Evernote 和邮件
-  拖入图片、文件即可发送
-  群聊 @ 提及成员
-  原生应用体验，未读消息小红点、消息通知等数十项优化
-  去除外链重定向，直接打开淘宝等网站
-  没有原生客户端万年不修复的bug

## 如何使用

在下载和运行这个项目之前，你需要在电脑上安装 [Git](https://git-scm.com) 和 [Node.js](https://nodejs.org/en/download/) (来自 [npm](https://www.npmjs.com/))。在命令行中输入:

``` bash
# 下载仓库
git clone https://github.com/geeeeeeeeek/electronic-wechat.git
# 进入仓库
cd electronic-wechat
# 安装依赖, 运行应用
npm install && npm start
```

根据你的平台打包应用:

``` shell
npm run build:osx
npm run build:linux
npm run build:win
```

**提示:** 如果 `npm install` 下载缓慢，你可以使用 [淘宝镜像(cnpm)](http://npm.taobao.org/) 替代 npm 。

**新渠道:** 使用你熟悉的包管理工具安装。请查看 [社区贡献的镜像](https://github.com/geeeeeeeeek/electronic-wechat/wiki/System-Support-Matrix#%E7%A4%BE%E5%8C%BA%E8%B4%A1%E7%8C%AE%E7%9A%84%E5%AE%89%E8%A3%85%E5%8C%85) 。

**新渠道:** homebrew 安装也已支持 (更新至 electronic-wechat v1.2.0)！

```bash
brew cask install electronic-wechat
```

#### [下载开箱即用的稳定版应用](https://github.com/geeeeeeeeek/electronic-wechat/releases)

#### 项目使用 [MIT](LICENSE.md) 许可

*Electronic WeChat* 是这个开源项目发布的产品。网页版微信是其中重要的一部分，但请注意这是一个社区发布的产品，而 *不是* 官方微信团队发布的产品。
