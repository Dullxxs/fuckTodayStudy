# <center>🏳️‍🌈今日校园自动签到脚本使用说明🏳️‍🌈</center>



<p align="center">
	<a href="https://github.com/thriving123"><img src="https://img.shields.io/badge/author-若离QQ:2909998156-green" /></a>
	<a href="#"><img src="https://img.shields.io/badge/type-签到脚本-orange" /></a>
    <a href="./LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue"/></a>
    <a href="https://blog.itruoli.com/archives/29.html"><img src="https://img.shields.io/badge/教程-博客-purple"/></a>
    <a href="https://pan.ruoli.cc/E5/video/"><img src="https://img.shields.io/badge/教程-视频-red"/></a>
    <a href="https://jq.qq.com/?_wv=1027&k=8gnv52Vc"><img src="https://img.shields.io/badge/QQ群-870967170（密码：子墨）-brightgreen" /></a>





#### 🙏小声BB：求求大哥们给个star吧🙏

#### 🙏小声BB：求求大哥们给个star吧🙏

#### 🙏小声BB：求求大哥们给个star吧🙏



## 👑项目说明

本项目严禁用于收费相关业务，您可以借助本项目进行二次开发或者完善

项目借助于腾讯云的`云函数`或者阿里云的`函数计算`亦或者`自己服务器/电脑`运行

请在使用本项目之前确保您拥有以上三个环境之一。

## 🏷下载项目

您只需要选择下载本项目，点击项目主页上面的`Code`菜单下面的`Download Zip`以下载最新版的源码

然后解压到您想存放的路径即可

## 📝编辑配置文件

#### 本地测试（如果您能确保您足够熟练能够使用本项目请忽略这个步骤）

说明：本地测试的作用是为了便于您完成配置文件的修改。

1. 请先确保您拥有`python3`及以上的环境，若您的电脑没有`python3`的环境请[👉点击下载👈](https://www.python.org/ftp/python/3.9.6/python-3.9.6-amd64.exe)

2. 当您拥有`python3`环境~~时~~之前，请确保您在安装的时候有选择`Add python3.9 to Path`的选项以配置好环境变量，否则请自行百度配置好`python3`的环境变量（此步骤的作用是让我们能够直接在命令行中输入`pip`/`pip3`的命令来安装依赖）

3. 现在，我们就可以通过~~记事本~~[VSCode](https://az764295.vo.msecnd.net/stable/379476f0e13988d90fab105c5c19e7abc8b1dea8/VSCodeUserSetup-x64-1.59.0.exe)/[Notepad++](https://en.softonic.com/download/notepad-plus/windows/post-download)（不推荐使用记事本，这里提供两种常用的`代码编辑器`和它的下载地址，点击名称即可进入下载）来编辑配置文件

4. 进入`fuckTodayStudy/今日校园`文件夹，右键单击`config.yml`选择之前安装的`代码编辑器`来编辑它

5. 在编辑期间请特别注意`config.yml`的格式，如缩进、空格等内容。

6. 配置文件一共拥有多个`-user:`，每个`-user:`开始到下一个`-user:`之间为一个账号的配置，您可以在这里配置多个用户，当然，`config.yml`中拥有多种不同`签到类型`的配置文件，请删除多余的用户配置，只保留您所以需要的`-user:`配置，每个`-user:`上面都拥有着该用户配置文件模板的`签到类型`说明，请选择好适合您的签到类型填上适当的配置信息（`forms:`表单内的`title`和`value`暂时不用填写，待会儿调试的时候来修改它）

8. 在调试的之前，您最好将`config.yml`顶部上面的`debug: `从false改为true以更好的定位到您的错误在哪里发生的

9. 在您配置完成`config.yml`之后，您就可以在同`config.yml`的当前目录下。找到`文件资源管理器`的`地址栏`（也就是您的文件夹显示窗口的顶部那一栏路径栏），单击空白处，清空路径地址，输入`cmd`回车以打开`cmd`界面

10. 安装依赖：到这一步，您就可以开始执行以下命令开始安装依赖了。在`cmd`中~~输入~~粘贴上以下代码按回车即可安装依赖

    `pip3 install -r requirements.txt -i https://mirrors.aliyun.com/pypi/simple`

    若出现`pip3 is not function`类似字眼，请确保您拥有`python3`环境并且配置了`环境变量`（请回看本地测试第1、2步）

    一般情况下安装过程中出现黄色字体可以无视，出现红色字体代表安装依赖出现错误，请在群里询问相关的问题

10. 当您安装完成依赖后，就可以开始进行**本地测试**（这么多步骤终于到了测试的这一个步骤了，感动到自己有木有！）了

    （请在测试之前确保您当日有表单并且还未提交）

    同样的在该`cmd`中输入`python index.py`并运行即可，在这里，您可能会遇到各种各样的错误

    - `No module named xxx`：出现这个情况代表您的依赖没有安装好，请仔细查看本地测试第9步
    - `list out of range`：应该是您的表单的问题较多，但是您的`config.yml`配置文件的`forms里的-form:`字段不够造成的，请多添加几个`-form`字段
    - `您的标题不正确 xxxx`：这是本地调试的主要作用，用于配置好您的学校对应的表单的标题和答案，请复制此cmd提示的标题来替换您`config.yml`中对应的`title`字段
    - `验证码识别出现问题了xxx`：这代表您的学校必须要填写验证码才能登录，请打开`/login`目录里的`system.yml`，配置好您的`SecrectId`和`SecretKey`（腾讯OCR开通地址：[点击这里](https://console.cloud.tencent.com/ocr/overview)，腾讯访问密钥开通地址：[点击这里](https://console.cloud.tencent.com/cam/capi)）
    - `success`：代表签到成功，若您未签到成功请反馈BUG
    - `其他问题`：请在群里提问，相信很多`大佬`都会为您解答。

    关于提问请在确定是bug之类的时候再来找我，请确定是自己的问题的时候多在群里提问，请勿提问已经说明的问题情况。

12. 当您的各种`title`和`value`配置完成，那么基本上就可以完成您当日的表单提交了。到这里，本地测试就已经完成了

## ☁打包上云！（自动化签到的关键）

到这里，您的本地测试就已经完成了。那么您的配置文件已经没有任何问题，可以部署到云端以自动化签到了

**特别强调：请注意以下`打包`是打包`xx文件夹里的内容`还是`xx文件夹`**

#### ☁打包上腾讯云

😑不推荐您使用腾讯云😑

😑不推荐您使用腾讯云😑

😑不推荐您使用腾讯云😑

之所以不推荐您部署到腾讯云，是因为部署到腾讯云会出现一些其他问题

诸如`418`，`405`等等的返回代码报错，遇到这种情况请记得更换云函数的地域（如何更换请仔细注意，创建的过程会选择它）

1. 在腾讯云[云函数](https://console.cloud.tencent.com/scf/list?rid=1&ns=default)中新建项目

2. 选择自定义创建（函数类型：事件函数；函数名称：随意（`fuckCampusHoy`）；地域：北京（这就是地域，若控制台出现418错误，请在这里更换地域）；部署方式：代码部署；运行环境：`python3.6`；函数代码：本地上传zip包）

3. 将`fuckTodayStudy/今日校园`里的所有文件整体打包成一个ZIP文件夹（进入`今日校园`文件夹`CTRL+A`全选，右键，压缩到`xxx.zip`文件夹）

4. 回到云函数创建页面，您可点击`上传`按钮以选择刚才您创建的zip压缩文件

5. 打开高级配置。其他随意，您应该将其中的`内存：`改大一点如256MB，`执行超时时间：`改为60（推荐值），单个用户25s左右，请自行计算时间。一般设置大一点比较好

6. 到这里您就配置好云函数的配置了，请您点击`完成按钮`以完成项目的初始化，请您耐心等待项目创建成功......

7. 待您创建完成云函数后，请您点击`函数代码`以打开编辑器界面

8. 请您点击`函数代码`里的`在线编辑器`中的`终端`里的`新建终端`以创建一个终端

9. 执行以下代码以安装您的依赖到云函数中

   `pip3 install -r ./src/requirements.txt -t ./src -i https://mirrors.aliyun.com/pypi/simple`

10. 若您成功安装依赖，那么您的`在线编辑器`大致将如下图所示，左侧增加了一坨文件夹，底部有个黄色的`WARNING`提示

    ![示例](https://cdn.jsdelivr.net/gh/thriving123/ruoliCdn@main/images/202108161455188.png)

11. 特别的，在这里当您安装完成依赖后，您需要往下滑动，点击一下`部署`按钮以保存您在云函数上的操作，等待您的云函数部署成功之后，即可点击测试按钮以完成您的测试，当出现`SUCCESS`并且返回字段也是`SUCCESS`代表您在云函数上没有任何问题了

12. 若您没有进行`本地测试`，请注意看这里，您现在可以返回到`本地测试`的第`4.5.6.10.11`步骤以完成您的`config.yml`的配置。若您之前进行了本地测试请您忽略本步骤

13. 既然测试完成，那么就开始实现每天的自动化签到了。请您在刚才的网页页面上，找到`触发管理`并打开它，`创建触发器`。在`触发周期上`选择`自定义触发周期`，在`Cron表达式`中输入`1 0 0/8/18/23 * * * *`（本`cron表达式`代表每天的0、8、18、23点01分执行一次）（更多`cron表达式`请自行查看它的规则）

14. 点击提交即可完成自动化签到的部署了

15. ✈**Now, enjoy it please！**~~（子墨师兄的口头禅）~~✈

#### ☁打包上阿里云

阿里云和腾讯云的区别：阿里云的层管理有点问题，~~同时阿里云没有`终端`功能，没法使用`pip`命令安装依赖~~。函数入口和阿里云有区别（对您而言这个没区别）

😝强烈推荐使用阿里云😝

😝强烈推荐使用阿里云😝

😝强烈推荐使用阿里云😝

（温馨提示，函数计算的新版代码编辑器有好些BUG，敬请期待它的完善吧！）

1. 在阿里云[函数计算 FC](https://fc.console.aliyun.com/fc/overview/cn-hangzhou)上，左上角选择好您要创建函数的的地区，左侧选择服务及函数

2. 新建一个服务，随意填写（英文）名称啥的，然后提交

3. 在该服务下`新建`一个函数；选择`事件函数`下的`配置部署`；设置号`函数名称`（英文）；`运行环境：Python3`；代码包上传；`高级设置`修改号内存和时间等

4. [点击这里](https://pan.ruoli.cc/E5/fuckToday/dependency.zip)下载`dependency.zip`以下载对应的依赖到本地

5. 回到`fuckTodayStudy`目录，将`dependency.zip`用压缩工具打开，全部解压到`fuckTodayStudy/今日校园`这个路径，也就是将`依赖`放到`今日校园`目录，

   ![示例](https://cdn.jsdelivr.net/gh/thriving123/ruoliCdn@main/images/202108161521709.png)

   然后再次全选`fuckTodayStudy/今日校园`里的代码`CTRL+A`全选，邮件，压缩成`xxx.zip`压缩文件

6. 回到函数计算网页，点击上传代码以上传压缩包（自行选择好您之前压缩的`xxx.zip`文件），然后点击`新建`即可，在这里您将等待一个漫长的漫长的漫长的时间...

7. 等待函数新建成功，进入到代码编辑，若您没有进行`本地测试`，请注意看这里，您现在可以返回到`本地测试`的第`4.5.6.10.11`步骤以完成您的`config.yml`的配置。若您之前进行了本地测试请您忽略本步骤

8. 点击`执行`按钮即可完成阿里云的函数部署，若报错请反馈报错代码截图（请确保本地运行正确先！）

9. 打开`触发器`，`创建触发器`，`服务类型：定时触发器`选择cron表达式，输入cron表达式如`0 0 7,12,14 * * *`代表7点、12点、14点各运行一次。自己输入`触发器名称`点击确定即可。

10. 点击提交即可完成自动化签到的部署了

11. ✈**Now, enjoy it please！**~~（子墨师兄的口头禅）~~✈

## ✅关于推送

现在，您可以配置邮件推送和`qmsg`推送了呢！

以下配置均在`config.yml`中进行修改

- 邮件推送：

  若您使用邮件推送，仅仅只需要配置好您的`sendType`为`0`即可

  同时您需要配置的有`emailApiUrl`（目前项目免费提供一个）和`sendKey`字段（您的邮箱如`xxx@qq.com`）

- QMSG推送：

  若您使用QMSG推送，仅仅只需要配置好您的`sendType`为`1`即可

  同时您需要配置的有`myQmsgKey`（qmsg酱生成的）和`sendKey`字段（您的已经在QMSG酱上绑定号的一个QQ号码）

- pushplus推送：

  若您使用pushplus推送，仅仅只需要配置好您的`sendType`为`2`即可

  同时您需要配置的有`sendKey`字段（pushplus的token）

当您配置好以上内容后，将会进行消息推送

## ⚠更新通知

- 修复信息收集的表单处理BUG ` v1.1.3`
- 完善通知功能
- 修复部分cas学校登录失败返回405无法正确获取cookies的bug
- 新增登陆适配`武汉轻工大学`，模块为`whpuLogin`，修复文档，`v1.1.2`
- 新增查寝模块`sleepCheck`，添加`debug`模式，可在`config.yml`中修改，用以找到错误是哪个位置 `v1.1.1`
- 新增邮件推送开关，当`config.yml`中的`- user`里的`email`为如下格式：`email: ''`，将不推送邮件 `v1.1.0`
- 新增一个`cas`学校的登陆（河南大学），新增`henuLogin`模块 `v1.0.9`
- 完成邮件推送功能 `v1.0.8`
- 修复签到值错误但不提示的bug `v1.0.7`
- 完成`教师端`的`工作日志`：新增`workLog`类 `v1.0.6`
- 制作视频，提取`Utils`公用模块 `v1.0.5`
- 修复签到失效 `v1.0.4`
- 完成`签到任务`，新增`autoSign`模块，修复bug `v1.0.3`
- 完成`iap`学校的登陆，新增`iapLogin`模块完善文档 `v1.0.2`
- 完成部分通用`cas`学校的登陆适配，并完成`信息收集`，新增`casLogin`模块和`collection`模块 `v1.0.1`
- 项目初始化（克隆自`子墨师兄`的代码）`v1.0`，新建`ruoli`分支并在其上魔改
