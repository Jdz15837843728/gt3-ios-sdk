# GT3Captcha Project

## 概述

极验验证3.0 iOS SDK提供给集成iOS原生客户端开发的开发者使用, SDK不依赖任何第三方库。

* **Bitcode版本**在`Bitcode`目录下的`GT3Captcha.framework`
* **非Bitcode版本**在`GT3Example`目录下的`GT3Captcha.framework`

## 环境需求

条目	|			|
------	|---------|
开发目标|兼容iOS7, 推荐iOS8+|
开发环境|Xcode 8.0|
系统依赖|`Webkit.framework`, `JavascriptCore.framework`|
SDK三方依赖|无		|

## 获取SDK

### 使用`git`命令从Github获取

```
git clone https://github.com/GeeTeam/gt3-ios-objc.git
```

### 手动下载获取
使用从github下载`.zip`文件获取最新的sdk。

[Github: gt3-ios-objc](https://github.com/GeeTeam/gt3-ios-sdk)

## 使用

`GT3Captcha.framework`是`Static Library`, 支持iOS7+

*如需动态库, 请联系极验技术。`Dynamic Library`仅支持iOS8+.*

使用参见根部目录下的`GT3Example`demo工程, demo包含以下场景

1. 在登录使用sdk默认封装接口`LoginViewController`
2. 在注册使用sdk默认封装接口`RegisterViewController`
3. 在自定义按钮下使用sdk默认封装接口`CustomButton`
4. 在自定义按钮下使用自定义接口`AsyncButton`

demo以iOS8作为示例, 语言默认支持中文简体、中文繁体、英文，但需要在`.plist`里添加如下属性(已存在的不用再次添加):

```xml
<key>CFBundleLocalizations</key>
	<array>
		<string>en</string>
		<string>zh_CN</string>
		<string>zh_TW</string>
	</array>
```

iOS7 不支持`Dynamic Library`, 所以无法使用`embedded binaries`. 而`Dynamic Library`无法获取`.strings`等资源文件, 如需自定义按钮的标题请查阅[`tipsDict`](https://github.com/GeeTeam/gt3-ios-sdk/blob/develop/gt3-ios-dev-doc.md#tipsdict)相关定义

极验验证3.0服务介绍[服务介绍](http://docs.geetest.com/install/overview/)

SDK安装教程见[官方文档](http://docs.geetest.com/install/client/ios/)

SDK接口文档见[接口文档](https://github.com/GeeTeam/gt3-ios-sdk/blob/develop/gt3-ios-dev-doc.md)

## 接口

集成前需要先了解极验验证3.0的[产品结构](http://docs.geetest.com/install/overview/#产品结构), 并且必须要先在您的后端搭建相应的**服务端SDK**，并配置从[极验后台](https://account.geetest.com/login)获取的`<gt_captcha_id>`和`<geetest_key>`用来配置您集成了极验服务端SDK的后台。

其中iOS SDK主要提供以下接口:

1. 配置验证初始化
2. 启动验证
3. 验证生命周期的代理方法
	* 错误处理
	* 结果处理
	* 流程控制 

## 更新日志

* **0.8.10:** 修复潜在bug; 增强统计接口;
* **0.8.8:** 修复潜在的crash问题; 修复内存泄漏; 增加debug代理;
* **0.8.6:** 紧急修复`openURL:`在iOS11上导致的crash问题;
* **0.8.5:** 优化高度获取方案; 其他问题修复;
* **0.8.1:** 修复iOS8+网络bug; 细节优化;
* **0.7.10:** 错误统一; ui逻辑调整;
* **0.7.6:** 改善数据; 其他问题修复;
* **0.7.2:** 改善数据交互; 增加forbidden事件;
* **0.6.3:** 修复onepass下没有图形提示的问题; 修复因状态不一致导致的server返回'runtime error';
* **0.6.2:** 解决0.6.1版在部分情况下, 执行动画导致cpu高消费; 解决已发现在数据层面导致的服务端返回'runtime error'的问题
* **0.6.1:** 针对按钮绑定集成验证优化；针对反馈提供更多新接口；改善初始化体验；提供更详实的演示demo 
* **0.5.7:** 修正`NSBundle`在非embedded binaries中的问题
* **0.5.6:** 修改提示文案；`GTCaptchaManagerViewDelegate`方法更新；验证成功后再次验证只需要点击一次；
* **0.5.5:** 对`GT3CaptchaButton`增加可选的代理方法
* **0.5.4:** 完善验证管理器生命周期
* **0.5.3:** 修复在未检测到传感器的情况下的表现行为；优化销毁逻辑
* **0.5.2:** 修改多交互逻辑, 界面适配修正
* **0.5.0:** 变更为静态库以支持iOS7；支持静默验证；少量修复和改善 