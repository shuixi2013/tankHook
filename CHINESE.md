[![VA banner](https://raw.githubusercontent.com/asLody/VirtualApp/master/Logo.png)](https://github.com/asLody/VirtualApp)

简介
---
**VirtualApp**是一个**App虚拟化引擎**（简称`VA`）。

**VirtualApp已兼容Android 0(8.0)。**

VirtualApp在你的App内创建一个`虚拟空间`，你可以在虚拟空间内任意的`安装`、`启动`和`卸载`APK，这一切都与外部隔离，如同一个`沙盒`。

运行在`VA`中的APK无需在外部安装，即VA支持**免安装运行APK**。

VA目前被广泛应用于双开/多开、应用市场、模拟定位、一键改机、隐私保护、游戏修改、自动化测试、无感知热更新等技术领域，但它决不仅限于此，Android本身就是一个极其开放的平台，免安装运行APK这一Feature打开了无限可能--------这都取决于您的想象力。

申明
---
VirtualApp在2017年8月份正式公司化运作，当您需要将VirtualApp用于商业用途时，请联系QQ：10890 购买商业授权。您如果未经授权将VirtualApp的代码作为您自己的代码用于内部使用、商业牟利或上传软件市场，我们将直接报警（侵犯著作权罪）或起诉，这将对您所属公司造成刑事责任及法律诉讼，影响到您公司的商誉和投资。<br/>
<br/>
目前VirtualApp拥有各行业众多授权客户，集成VirtualApp代码的APP日启动量超过2亿次。购买商业授权为您所在公司节省大量开发完善时间，保障产品高效上线运营，让您有更多时间用于创新及盈利。获取VirtualApp商业授权后您将得到：商业版代码、说明接入文档、微信和QQ群技术支持。<br/>
<br/>
负责人：张总<br/>
手机：130-321-77777<br/>
Q Q：10890<br/>
<br/>
商业版代码保持每月1-2次以上频率持续更新，并对Android 8.0进行大量适配，保证了兼容性。<br/>

 
商业版更新日志：

**2018年03月13日**
1. 修复某些rom下，快捷方式图标不正确
2. 兼容以前组件StubFileProvider
3. 适配部分新ROM的虚拟IMEI

**2018年03月12日**
1. 改善进程初始化代码，增加稳定性

**2018年03月11日**
1. 添加内部发送Intent.ACTION_BOOT_COMPLETED的广播，可以设置开关

**2018年03月09日**
1. 适配关联google play游戏，支持游戏使用google登录

**2018年03月08日**
1. 适配android O的google service框架

**2018年03月07日**
1. 适配android O 快捷方式
2. 适配耳机模式
3. 某些rom对intent的大小限制，demo添加缩放快捷方式图标代码
4. 修复多开情况下一个bug

**2018年03月02日**
1. 修复某些情况下MediaController的bug
2. 修复4.1.2的StubFileProvider报错

**2018年02月07日**
1. 分享的uri处理
2. 修复跨app调用Activity的回调

**2018年02月05日**
1. 前台服务的通知栏拦截开关
2. 附带doc

**2018年02月03日**
1. 完善VA内部的intent的CHOOSE回调

**2018年01月29日**
1. Android O的通知栏适配2

**2018年01月22日**
1. ipc框架优化, 提高判断binder的存活准确性

**2018年01月15日**
1. jni的log开关 Android.mk:LOCAL_CFLAGS += -DLOG_ENABLE
2. 混淆配置
3. Android O的通知栏适配

**2018年01月14日**
1. 修复部分app网络卡的问题

**2018年01月12日**
1. 适配 android 8.0的dl_open（jni加载）

**2018年01月09日**
1. 修复华为emui8.0的一个bug

**2018年01月08日**
1. 完善定位
2. 设置手机信息，imei伪装算法
3. 适配8.0某个功能（主要app：whatsapp）
4. 修复内部微信等应用，无法更新图片，视频
5. demo增加安装监听，自动升级克隆模式的应用
6. 7.0的file provider适配

**2017年12月28日**
1. 增加了定位代码
2. 代码进行了架构优化
3. 与开源版不同的特征
4. 解决了微信被封的一些问题
5. 修复了部分机型兼容性
6. 修复了12个小BUG


已支持的加固(不断更新)
----------
* 360加固
* 腾讯加固
* 梆梆加固
* 梆梆企业版(12306客户端 Pass)
* 爱加密
* 百度加固
* 娜迦加固
* 乐变加固
* 网易易盾
* 通付盾
* (已支持的加固均可通过VA来脱壳，本技术不公开)


Google Play Framework
-----------
在google service新版本，存在兼容适配问题，暂时屏蔽


使用说明
----------

**前往你的Application并添加如下代码:**
```java
    @Override
    protected void attachBaseContext(Context base) {
        super.attachBaseContext(base);
        try {
            VirtualCore.getCore().startup(base);
        } catch (Throwable e) {
            e.printStackTrace();
        }
    }
```
**安装App:**
```java
    VirtualCore.getCore().installApp({APK PATH}, flags);
```
**启动App:**
```java
    VirtualCore.getCore().launchApp({PackageName});
```
**移除App:**
```java
    VirtualCore.getCore().uninstallApp({PackageName});
```
**该App的基本信息:**
```java
    VirtualCore.getCore().findApp({PackageName});
```

BUG反馈
------------
zl@aluohe.com
