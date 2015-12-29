# ISV接入指南

钉钉开放平台提供了**企业通讯录管理、文件管理、发送企业会话消息**等功能，接口使用可以参考[<font color=red >服务端开发文档</font>](#服务端开发文档)；

我们定制了微应用专用的运行容器，提供了一组可以调用**钉钉的本地能力和业务逻辑**的JS接口，开发者可以通过这些接口使用钉钉的本地能力或者钉钉的业务逻辑，降低开发成本，提高微应用在移动客户端的体验。接口使用可以参考[<font color=red >客户端开发文档</font>](#客户端开发文档)。

该指南主要介绍了企业和ISV（服务提供商）如何接入钉钉开放平台，其中涉及到接入过程中使用的工具、与钉钉开放平台相关的概念和接入钉钉开放平台的一些实践方法，以帮助开发者快速开发自己的微应用。


## 接入准备

开发者在使用钉钉开放平台开发微应用前需做好以下准备：

- 注册钉钉企业；
- 服务端环境搭建和域名注册；
- 开发环境搭建；

### 注册钉钉企业账号
一、进入 [<font color=red >钉钉管理后台</font>](https://oa.dingtalk.com) 页面, 点击 [<font color=red >企业注册</font>](https://oa.dingtalk.com/register.html?spm=0.0.0.0.dL51oc)；（已经注册可跳过此步骤）

![enterprise_register_entry](https://img.alicdn.com/tps/TB14kI8IFXXXXciapXXXXXXXXXX.jpg)

二、填写注册手机号码和短信验证码；

三、输入企业基本信息和管理员帐号和密码，点击 *注册* 按钮完成注册过程。

![input_enterprise_info](https://img.alicdn.com/tps/TB1bru8JFXXXXXcXFXXXXXXXXXX-1171-807.png)

<aside class="notice">
通过钉钉移动客户端创建的企业默认没有设置钉钉后台管理员，需要通过以上流程注册管理员帐号。
</aside>

#### 分配管理员子账号：

一、登录钉钉后台管理系统，按下图进入安全中心的添加管理员子帐号页面；

![add_sub_manager](https://img.alicdn.com/tps/TB1Q3DiJFXXXXbkXXXXXXXXXXXX-1147-377.png)

二、按下图提示填写子帐号信息

![set_sub_manager_account](https://img.alicdn.com/tps/TB16euYJFXXXXcRXFXXXXXXXXXX-601-336.png)

完成管理员子帐号设置后，子帐号关联的钉钉用户会在钉钉客户端的 *钉小秘* 会话中收到管理员帐号和初始密码，该钉钉用户可以通过收到的帐号和密码登录 [<font color=red >钉钉管理后台</font>](https://oa.dingtalk.com) 进入安全中心对初始密码进行修改。

### 服务端环境搭建和域名注册

开发者可以自己搭建服务器也可以购买云主机来搭建自己的服务端环境，开发者需要为自己的微应用注册合法有效的域名

### 开发环境搭建

钉钉开放平台的服务端接口不区分语言和平台，开发者可以使用自己熟悉的技术搭建开发环境来开发微应用


至此，您已经完成了准备工作。

假如你是企业用户，要为自己的公司开发微应用，查看[<font color=red >企业接入</font>](#企业接入)。

假如你是ISV(服务提供商)，作为第三方要给其他公司提供微应用，先查看[<font color=red >ISV接入</font>](#isv接入)。


## ISV接入整体流程

![ISV process](https://img.alicdn.com/tps/TB1fDX4LXXXXXa2XpXXXXXXXXXX-1009-367.png)
### ISV接入说明

ISV接入钉钉后有2种选择：

- 套件通过钉钉应用中心推广（精品套件），符合接入[<font color=red>整体流程</font>](#isv接入整体流程)中的要求，并满足[<font color=red>标准规范</font>](#标准规范)中的要求，需要通过钉钉应用中心推广必须与钉钉进行商务洽谈，商务洽谈联系方式：[<font color=red>商务洽谈</font>](#商务洽谈)

- 套件通过ISV线下推广，可以通过2种方式进行操：

1.通过企业接入的方式，为企业单独进行接入

2.通过钉钉快速部署进行实施，详细内容见[<font color=red>钉钉快速部署指南</font>](#钉钉快速部署指南)中的描述。使用此方式需满足[<font color=red>标准规范</font>](#标准规范)中的要求，钉钉团队会进行质量验收，其它项由ISV自己负责，如果接收到用户的投诉，钉钉保留对ISV的处罚权利

### 商务洽谈

ISV联系钉钉ISV接入接口人进行合作洽谈，更多信息请通过联系方式：angle.lixy@alibaba-inc.com 进行

### 钉钉快速部署指南
#### ISV接入准备
1.ISV使用快速部署必须先实现[<font color=red>ISV套件对企业独立部署方案</font>](#isv套件对企业独立部署方案)

2.ISV需要在云市场提交商品审核，套件上架流程详见：[<font color=red>套件上架流程</font>](#套件上架操作流程)


![Application Form](https://img.alicdn.com/tps/TB1c3uBLXXXXXaNXXXXXXXXXXXX-802-571.png)


栏位	| 填写要求
------- | -------------

![ksbs_process](https://img.alicdn.com/tps/TB1xcWaLXXXXXcIXVXXXXXXXXXX-863-585.png)

实施步骤：


![DD_QRcode](https://img.alicdn.com/tps/TB1HeydLXXXXXaJXVXXXXXXXXXX-584-584.png)

2.提交快速部署后，钉钉工作人员会通过邮件，发送套件二维码给ISV, 客户通过钉钉手机端上的扫码工具，扫描进入快速部署引导页

![DD_ksbs1](https://img.alicdn.com/tps/TB1n7qhLXXXXXXhXVXXXXXXXXXX-427-640.png)

3.创建团队：配置可以选择创建1人团队（大于等于1人），或多人团队（大于等于6人），



![DD_ksbs2](https://img.alicdn.com/tps/TB17wWoLXXXXXcTXpXXXXXXXXXX-394-652.png)

4.开通微应用：分为3步：：输入应用序列号－立即授权－使用范围设置



![DD_ksbs3](https://img.alicdn.com/tps/TB18Hx9LXXXXXbeaXXXXXXXXXXX-427-706.png)

4.2：立即授权

![DD_ksbs4](https://img.alicdn.com/tps/TB1Ic9CLXXXXXaxXXXXXXXXXXXX-438-720.png)

4.3：设置使用范围，设置微应用哪些员工可以使用

![DD_ksbs5](https://img.alicdn.com/tps/TB1iV5nLXXXXXcaXpXXXXXXXXXX-449-780.png)

4.4 开始使用， 用户点击“开始使用”可以进入手机端工作界面页

![DD_ksbs6](https://img.alicdn.com/tps/TB190CBLXXXXXa.XXXXXXXXXXXX-450-729.png)
![DD_ksbs7](https://img.alicdn.com/tps/TB17ceELXXXXXXtXXXXXXXXXXXX-504-702.png)

4.5  开通授权后，isv可获取团队邀请链接，团队邀请链接处理逻辑


## 注册钉钉开发者

### 描述（Description）

阿里云用户登录后，在通过实名认证的情况下，填写相关信息，完成开发者的身份申请。

### 前置条件（Pre-Conditions）

申请者首先是阿里云用户

### 基本流程（Basic Flow）

#### a. 点击进入[<font color=red >控制台</font>](http://console.d.aliyun.com)，进行登录。

#### b. 登录阿里云账号

#### c. 进行实名认证（已经实名认证过的开发者直接看g.步骤）

用户未通过实名认证，需要实名认证后，才能申请开发者，流程如下：

#### d. 点击“立即认证”

![lijirz](https://img.alicdn.com/tps/TB1PUwmIVXXXXbbXXXXXXXXXXXX-866-305.png)

#### e. 新开窗口跳转到阿里云认证页面

![shimingrz](https://img.alicdn.com/tps/TB1lv3iIVXXXXa6XpXXXXXXXXXX-866-412.png)

#### f. 实名认证通过，在弹窗点击“立即刷新”按钮

![zhengzairz](https://img.alicdn.com/tps/TB11m_VIVXXXXaqapXXXXXXXXXX-866-334.png)

#### g. 显示已通过实名认证

![shiming](https://img.alicdn.com/tps/TB1C3T6IVXXXXXWaXXXXXXXXXXX-866-335.png)

#### h. 选择开发应用类型为“钉钉企业类型”，填入“钉钉企业账号”
##### 数据项说明

字段  		| 属性
-----------	| -------------
开发者介绍	| 100字
开发应用类型	| 选择“钉钉企业账号”
钉钉企业账号 	| 4-11位小写英文字符、数字、下划线
账号密码 		| 必须为6位以上数字、大小写字母的组合

#### i. 显示申请开发者成功


## 创建套件&微应用

### 1: 创建套件

#### 1.1 描述（Description）

在开发钉钉应用前，首先要创建一个套件，套件可以包含一组应用，并对这组应用统一进行权限管理。

#### 1.2 前置条件（Pre-Conditions）

阿里云用户成功申请开发者

#### 1.3 基本流程（Basic Flow）

##### a.钉钉应用菜单-套件列表，点击“创建套件”

![createtj](https://img.alicdn.com/tps/TB1fyqYJFXXXXcXXVXXXXXXXXXX-1346-479.jpg)

##### b．填写创建套件表单

![createtjbd](https://img.alicdn.com/tps/TB1Az_EJFXXXXb3XFXXXXXXXXXX-678-539.jpg)

##### 数据项说明：

字段  		| 属性
-----------	| -------------
套件Logo		| 上传大小不超过1M，长宽等比且范围在50px至200px之间的png格式图片
回调URL		| 以http://开头，系统将会把此套件的SuiteTicket，临时授权码以及授权变更事件推送给此URL，详细请看[<font color=red >回调接口</font>](#2-回调接口（分为五个回调类型）)
Token 		| 可任意填写，用于生成签名，校验回调请求的合法性。本套件下相关应用产生的回调消息都使用该值来解密。
数据加密密钥 	| 回调消息加解密参数，是AES密钥的Base64编码，用于解密回调消息内容对应的密文。本套件下相关应用产生的回调消息都使用该值来解密。
IP白名单		| 调用钉钉API时的合法IP列表，多个IP请以“,”隔开，如IP有变化，请立即更新
部署方式		| 选择ACE，系统接下来将自动开通基于ACE的开发环境，选择其他则需要自行准备开发环境
当前状态 		| 对于需要公开售卖的套件，只有处于已完成状态，才可进入售卖流程



**当您注册套件时，钉钉服务器为了避免无效推送，将会验证回调url的有效性，对回调url推送"验证回调URL有效性事件"，收到推送后您需要做正确的处理，才能成功创建套件。详细处理步骤请查看[<font color=red >回调接口</font>](#2-回调接口（分为五个回调类型）)和"验证回调URL有效性事件"。**

##### c.点击“确定”按钮进入套件列
在这里可以查看套件详细信息，比如套件Key（suite_key），套件secret(suite_secret)


### 2: 创建微应用


#### 2.1 描述（Description）

开发者编辑套件基本信息，创建微应用。

#### 2.2 前置条件（Pre-Conditions）

阿里云用户，申请成为开发者，套件列表点击“管理”操作

#### 2.3 基本流程（Basic Flow）

##### a 查看套件基本信息

##### b 点击“创建微应用按钮”

![createmini1](https://img.alicdn.com/tps/TB19X14JFXXXXc3XFXXXXXXXXXX-1164-326.jpg)

##### c 添加创建微应用表单，点击“确定”按钮

![createmini2](https://img.alicdn.com/tps/TB1G0nnJFXXXXa8XXXXXXXXXXXX-705-649.jpg)
##### 需要提供的数据项：

字段  		| 属性
-----------	| -------------
名称 		| 应用的名称，2-16个字。
图标 		| 上传大小不超过1M，长宽等比且范围在50px至200px之间的png格式图片
应用描述 		| 描述该应用的功能与特色，4-120个字内
主页地址	 	| 以http://开头，用于接收托管企业应用的用户消息，URL支持使用$CORPID$模板参数表示corpid，用户访问应用的时候将把$CORPID$替换成用户所属企业的corpid，例如http://www.dingtalk.com/index?corpid=$CORPID$
权限设置		| 多选
接口权限		| 多选


##### d 微应用列表添加一行记录

![createmini3](https://img.alicdn.com/tps/TB1V7DoJFXXXXarXXXXXXXXXXXX-1164-440.jpg)

### 3: 注册测试企业

#### 3.1.描述（Description）

钉钉套件在开发过程中，需要在钉钉移动端上登录绑定了相关企业的钉钉帐号来进行调试。在此之前，需要开发者对注册的测试企业"发起授权所有套件"，之后钉钉服务器会向您填写的回调url[<font color=red>推送临时授权码</font>](##2-回调接口（分为五个回调类型）)，您需要通过临时授权码一步一步到[<font color=red>激活授权套件</font>](#7-激活授权套件)，才能让测试企业的微应用列表出现您开发的微应用。

#### 3.2.前置条件（Pre-Conditions）

阿里云用户成功申请开发者

#### 3.3.基本流程（Basic Flow）

###### a.钉钉应用菜单—开发环境列表，点击“注册测试企业”

![signintest1](https://img.alicdn.com/tps/TB1VBWRJVXXXXXGaXXXXXXXXXXX-1022-78.jpg)
##### b.填写企业相关信息

![signintest2](https://img.alicdn.com/tps/TB1p1H3IVXXXXX8aXXXXXXXXXXX-729-447.png)

##### c.点击“确定”后列表增加一行记录

![signintest3](https://img.alicdn.com/tps/TB1pvqVJVXXXXahXVXXXXXXXXXX-1029-343.jpg)

##### d.点击“模拟测试企业发起授权所有套件”，弹窗提示微应用开通成功

注意：只有在微应用注册的回调接口能够接收推送，才能成功开通微应用，具体详情查看[<font color=red>回调接口</font>](#5-回调接口（分为五个回调类型）)

![signintest4](https://img.alicdn.com/tps/TB1B2njJVXXXXaEXXXXXXXXXXXX-1048-158.jpg)

##### e.点击“登录管理”跳转钉钉登录后台

![signintest5](https://img.alicdn.com/tps/TB1lEKUJVXXXXaSXVXXXXXXXXXX-1048-158.jpg)

![signintest6](https://img.alicdn.com/tps/TB1snUfIVXXXXbSXpXXXXXXXXXX-866-456.png)

## ISV接入开发指南

### 1: ISV接口调用整体流程
欢迎成为钉钉微应用的服务提供商！
通过接入钉钉ISV的应用授权接口，可以快速发布自己的微应用套件，引导企业客户自动开通微应用，将自己的服务快速触达到自己的目标客户！
钉钉的应用授权方案包含以下两个场景：

#### ISV注册应用

你，作为ISV若要使用此方案，只需在阿里云上注册成为第三方服务提供商，在ISV接入后台创建应用套件，并在应用套件中配置好相应的应用。
本方案所说的应用套件，是第三方应用授权的主体，它可以包含多个第三方所提供的同一类型的应用。目前一个第三方最多可以注册五个应用套件，一个应用套件最多可以包含五个应用。

#### 企业管理员授权应用

企业的管理员在钉钉企业后台的微应用列表中浏览你的应用套件后，即可发起一键授权，系统将展示微应用的第三方授权页面，管理员根据授权页面的引导，确认授权内容，完成授权操作。
授权完成之后，企业就可使用ISV服务提供商所提供的应用服务了。一切将变得简单自然。以下是详细的接口调用时序图
![Mou icon](https://img.alicdn.com/tps/TB1RhMGJXXXXXXdXVXXXXXXXXXX-876-659.jpg)

### 2: 回调接口（分为五个回调类型）
#### 使用场景

在使用回调接口之前您需要了解的是，

首先要拿到您创建套件时填写的"回调URL"，"Token"，"数据加密密钥(ENCODING_AES_KEY)"，

- 回调URL:服务提供商接收推送请求的协议和地址

- Token:服务提供商在注册时任意填写的，用来生成signature，用来和回调参数中的signature比对，校验消息的合法性

- 数据加密密钥(ENCODING_AES_KEY):用于消息体的加解密。

钉钉服务器会向服务提供商申请时填写的套件回调URL定时推送SuiteTicket，以及临时授权码和授权设置变更。

假设您提供的回调URL是

`https://127.0.0.1/suite/receive`

那么在钉钉服务器每一次访问回调URL的时候
将请求(下面链接中的signature,timestamp,nonce的值只是示例，并不代表真实返回的值):

`https://127.0.0.1/suite/receive?signature=111108bb8e6dbce3c9671d6fdb69d15066227608
&timestamp=1783610513&nonce=380320111`

```
{
	"encrypt":"1ojQf0NSvw2WPvW7LijxS8UvISr8pdDP+rXpPbcLGOmIBNbWetRg7IP0vdhVgkVwSoZBJeQwY2zhROsJq/HJ+q6tp1qhl9L1+ccC9ZjKs1wV5bmA9NoAWQiZ+7MpzQVq+j74rJQljdVyBdI/dGOvsnBSCxCVW0ISWX0vn9lYTuuHSoaxwCGylH9xRhYHL9bRDskBc7bO0FseHQQasdfghjkl"
}
```

回调数据的格式如右所示：

其中的encrypt字段是经过加密的消息体，encrypt经过一系列解密步骤后，才能产生下面所说的“POST数据解密后示例”，服务提供商可以直接使用钉钉提供的库进行解密的处理。

除此之外，在接收到推送之后，**需要返回相应的加密字符串（代表了你收到了推送）**，如果ISV未能成功返回，钉钉服务器将持续推送下去，达到100次后将不再推送。

"Talk is cheap, show me the code."所以我们也为开发者提供了加解密的demo，目前提供Java/PHP等语言版本。
加解密库和demo的下载：[<font color=red >加解密库和demo下载</font>](#加解密库和demo下载)

本地调试：[<font color=red >如何本地进行调试？</font>](#调试工具)

如有需要，可以查看具体加解密步骤：[<font color=red >查看</font>](#12-加解密方案)


#### 接口说明

#### a.<font color=red >验证回调URL有效性事件</font>

此事件的推送会发生在注册套件，点击下图按钮之时。注意，若未能成功验证回调URL有效性，套件将不能被创建。

![verifyurl](https://img.alicdn.com/tps/TB1RuHzJFXXXXahXVXXXXXXXXXX-615-100.jpg)

```
dingTalkEncryptor = new DingTalkEncryptor(Env.TOKEN, Env.ENCODING_AES_KEY, Env.CREATE_SUITE_KEY);//套件在创建中，使用默认的SUITE_KEY进行加解密

```

此时，由于套件尚未创建成功，还未生成套件的SUITE_KEY，所以在解密post数据的时候，需要使用默认的Env.CREATE_SUITE_KEY（默认值为"suite4xxxxxxxxxxxxxxx"）来解密，以java-demo代码为例（Env为Demo中配置文件），如右。


待成功处理『验证回调URL有效性事件』事件，套件创建成功之后，就不能再使用默认的SUITE_KEY了，需要使用套件本身的SUITE_KEY，所以需要在Env.java中配置SUITE_KEY，然后重新部署代码,此时将用下面的语句进行加解密。


`dingTalkEncryptor = new DingTalkEncryptor(Env.TOKEN, Env.ENCODING_AES_KEY, Env.SUITE_KEY);//套件创建成功后，使用套件本身的SUITE_KEY进行加解密`



POST数据解密后示例

```

{

  "EventType":"check_create_suite_url",
  "Random":"brdkKLMW",
  "TestSuiteKey":"suite4xxxxxxxxxxxxxxx"

}

```


参数      | 说明
-------   | -------------
Random  | 随机字符串
EventType | check_create_suite_url
TestSuiteKey  | 校验的SuiteKey

##### 返回说明

服务提供商在收到此事件推送后务必返回包含经过加密后"Random"字段的json数据，比如对于上面的示例，需要返回的即是加密后的"brdkKLMW"字符串。

只有返回了对应的json数据，钉钉才会判断此事件推送成功，套件才能创建成功。

```

{
  "msg_signature":"111108bb8e6dbce3c9671d6fdb69d15066227608",
  "timeStamp":"1783610513",
  "nonce":"123456",
  "encrypt":"1ojQf0NSvw2WPvW7LijxS8UvISr8pdDP+rXpPbcLGOmIBNbWetRg7IP0vdhVgkVwSoZBJeQwY2zhROsJq/HJ+q6tp1qhl9L1+ccC9ZjKs1wV5bmA9NoAWQiZ+7MpzQVq+j74rJQljdVyBdI/dGOvsnBSCxCVW0ISWX0vn9lYTuuHSoaxwCGylH9xRhYHL9bRDskBc7bO0FseHQQasdfghjkl" // "Random"字段的加密数据
}

```

参数      | 说明
-------   | -------------
msg_signature  | 消息体签名
timeStamp | 时间戳
nonce  | 随机字符串
encrypt  | "Random"字段的加密字符串

#### b: 定时推送Ticket

服务器会向服务提供商申请时填写的套件事件接收 URL定时（二十分钟）推送ticket：


服务提供商在收到ticket推送后务必返回经过加密的字符串"success"的json数据


如果不返回，钉钉服务器将连续推送，直到推送次数超过100次，就不再推送。倘若您希望钉钉服务器重新推送，需要进入[<font color=red>开发者后台</font>](http://console.d.aliyun.com)，进入套件管理页面，点击『重新推送』按钮，即可重新推送。
![repush](https://img.alicdn.com/tps/TB15j7OJFXXXXckXXXXXXXXXXXX-1121-124.jpg)

POST数据解密后示例

```
{
  "SuiteKey": "suitexxxxxx",
  "EventType": "suite_ticket ",
  "TimeStamp": 1234456,
  "SuiteTicket": "adsadsad"
}
```

参数			| 说明
-------		| -------------
SuiteKey	| 应用套件的SuiteKey
EventType	| suite_ticket
TimeStamp	| 时间戳
SuiteTicket	| Ticket内容

##### 返回说明

服务提供商在收到此事件推送后务必返回包含经过加密的字符串"success"的json数据

只有返回了对应的json数据，钉钉才会判断此事件推送成功，套件才能创建成功。

```

{
  "msg_signature":"111108bb8e6dbce3c9671d6fdb69d15066227608",
  "timeStamp":"1783610513",
  "nonce":"123456",
  "encrypt":"1ojQf0NSvw2WPvW7LijxS8UvISr8pdDP+rXpPbcLGOmIBNbWetRg7IP0vdhVgkVwSoZBJeQwY2zhROsJq/HJ+q6tp1qhl9L1+ccC9ZjKs1wV5bmA9NoAWQiZ+7MpzQVq+j74rJQljdVyBdI/dGOvsnBSCxCVW0ISWX0vn9lYTuuHSoaxwCGylH9xRhYHL9bRDskBc7bO0FseHQQasdfghjkl" // "Random"字段的加密数据
}

```

参数      | 说明
-------   | -------------
msg_signature  | 消息体签名
timeStamp | 时间戳
nonce  | 随机字符串
encrypt  | "success"加密字符串


#### c:回调向ISV推送临时授权码

当授权方（即授权企业）在微应用管理端的授权管理中，向服务提供商的应用套件授权了访问权限，钉钉服务器会向服务提供商的套件事件接收 URL（创建套件时填写）推送临时授权码，

比如在[<font color=red>钉钉开发者后台</font>](http://console.d.aliyun.com)中，模拟测试企业发起授权，钉钉服务器就会向回调url推送测试企业的临时授权码

![shouqun](https://img.alicdn.com/tps/TB1rZerKpXXXXX8XXXXXXXXXXXX-720-124.jpg)


收到临时授权码之后请按照步骤换取永久授权码，并将永久授权码存下来。

POST数据解密后示例

```
{
  "SuiteKey": "suitexxxxxx",
  "EventType": " tmp_auth_code",
  "TimeStamp": 1234456,
  "AuthCode": "adads"
}
```

字段说明

参数			| 说明
-------		| -------------
SuiteKey	| 应用套件的SuiteKey
EventType	| tmp_auth_code
TimeStamp	| 时间戳
AuthCode	| 临时授权码

##### 返回说明

服务提供商在收到此事件推送后务必返回包含经过加密的字符串"success"的json数据

只有返回了对应的json数据，钉钉才会判断此事件推送成功，套件才能创建成功。

```

{
  "msg_signature":"111108bb8e6dbce3c9671d6fdb69d15066227608",
  "timeStamp":"1783610513",
  "nonce":"123456",
  "encrypt":"1ojQf0NSvw2WPvW7LijxS8UvISr8pdDP+rXpPbcLGOmIBNbWetRg7IP0vdhVgkVwSoZBJeQwY2zhROsJq/HJ+q6tp1qhl9L1+ccC9ZjKs1wV5bmA9NoAWQiZ+7MpzQVq+j74rJQljdVyBdI/dGOvsnBSCxCVW0ISWX0vn9lYTuuHSoaxwCGylH9xRhYHL9bRDskBc7bO0FseHQQasdfghjkl" // "Random"字段的加密数据
}

```

参数      | 说明
-------   | -------------
msg_signature  | 消息体签名
timeStamp | 时间戳
nonce  | 随机字符串
encrypt  | "success"加密字符串


#### d:回调向ISV推送授权变更消息

当授权方（即授权企业）在微应用管理端中，修改了对套件的授权托管后，钉钉服务器会向服务提供商的套件事件接收 URL（创建套件时填写）推送授权变更消息。注意，推送的授权变更信息并不包括企业用户具体做了什么修改，所以收到推送之后,

**ISV需要通过调用[<font color=red >获取企业的应用信息</font>](#10-获取企业的应用信息)接口**，获取接口返回值其中的"close"参数，才能得知微应用在企业用户做了授权变更之后的状态，有三种状态码，分别为0，1，2.含义如下：

- 0:禁用（例如企业用户在OA后台禁用了微应用）
- 1:正常 (例如企业用户在禁用之后又启用了微应用)
- 2:待激活 (企业已经进行了授权，但是ISV还未为企业激活应用)

再根据具体状态做具体操作。比如状态为2，就需要ISV为企业进行激活授权套件的操作。

POST数据解密后示例

```
{
  "SuiteKey": "suitexxxxxx",
  "EventType": " change_auth",
  "TimeStamp": 1234456,
  "AuthCorpId": "xxxxx"
}
```

字段说明

参数			| 说明
-------		| -------------
SuiteKey	| 应用套件的SuiteKey
EventType	| change_auth
TimeStamp	| 时间戳
AuthCorpId	| 授权方企业的corpid

##### 返回说明

服务提供商在收到此事件推送后务必返回包含经过加密的字符串"success"的json数据

只有返回了对应的json数据，钉钉才会判断此事件推送成功，套件才能创建成功。

```

{
  "msg_signature":"111108bb8e6dbce3c9671d6fdb69d15066227608",
  "timeStamp":"1783610513",
  "nonce":"123456",
  "encrypt":"1ojQf0NSvw2WPvW7LijxS8UvISr8pdDP+rXpPbcLGOmIBNbWetRg7IP0vdhVgkVwSoZBJeQwY2zhROsJq/HJ+q6tp1qhl9L1+ccC9ZjKs1wV5bmA9NoAWQiZ+7MpzQVq+j74rJQljdVyBdI/dGOvsnBSCxCVW0ISWX0vn9lYTuuHSoaxwCGylH9xRhYHL9bRDskBc7bO0FseHQQasdfghjkl" // "Random"字段的加密数据
}

```

参数      | 说明
-------   | -------------
msg_signature  | 消息体签名
timeStamp | 时间戳
nonce  | 随机字符串
encrypt  | "success"加密字符串



#### e."套件信息更新"事件

此事件的推送会发生在更新套件信息的时候。

POST数据解密后示例

```

{
  "EventType":"check_update_suite_url",
  "Random":"Aedr5LMW",
  "TestSuiteKey":"suited6db0pze8yao1b1y"

}

```

服务提供商在收到"套件信息更新"事件推送后务必返回经过加密后"Random"字段，比如对于右边的示例，需要返回的即是加密后的"Aedr5LMW"字符串。


参数			| 说明
-------		| -------------
Random	| 随机字符串
EventType	| check_update_suite_url
TestSuiteKey	| 校验的SuiteKey(此处为套件的SuiteKey)

##### 返回说明

服务提供商在收到此事件推送后务必返回包含经过加密后"Random"字段的json数据，比如对于上面的示例，需要返回的即是加密后的"Aedr5LMW"字符串。

只有返回了对应的json数据，钉钉才会判断此事件推送成功，套件才能创建成功。

```

{
  "msg_signature":"111108bb8e6dbce3c9671d6fdb69d15066227608",
  "timeStamp":"1783610513",
  "nonce":"123456",
  "encrypt":"1ojQf0NSvw2WPvW7LijxS8UvISr8pdDP+rXpPbcLGOmIBNbWetRg7IP0vdhVgkVwSoZBJeQwY2zhROsJq/HJ+q6tp1qhl9L1+ccC9ZjKs1wV5bmA9NoAWQiZ+7MpzQVq+j74rJQljdVyBdI/dGOvsnBSCxCVW0ISWX0vn9lYTuuHSoaxwCGylH9xRhYHL9bRDskBc7bO0FseHQQasdfghjkl" // "Random"字段的加密数据
}

```

参数      | 说明
-------   | -------------
msg_signature  | 消息体签名
timeStamp | 时间戳
nonce  | 随机字符串
encrypt  | "Random"字段的加密字符串


#### f."解除授权"事件

此事件的推送会发生在企业解除套件授权的时候。

POST数据解密后示例

```

{
  "EventType":"suite_relieve",
  "SuiteKey":"suited6db0pze8yao1b1y",
  "TimeStamp":"12351458245",
  "AuthCorpId":"ding4583267d28sd61"
}

```

服务提供商在收到"解除授权"事件推送后务必返回包含经过加密的字符串"success"的json数据。


参数			| 说明
-------		| -------------
SuiteKey	| 应用套件的SuiteKey
EventType	| suite_relieve
TimeStamp	| 时间戳
AuthCorpId	|授权方企业的corpid

##### 返回说明

服务提供商在收到"解除授权"事件推送后务必返回包含经过加密的字符串"success"的json数据。

只有返回了对应的json数据，钉钉才会判断此事件推送成功。

```

{
  "msg_signature":"111108bb8e6dbce3c9671d6fdb69d15066227608",
  "timeStamp":"1783610513",
  "nonce":"123456",
  "encrypt":"1ojQf0NSvw2WPvW7LijxS8UvISr8pdDP+rXpPbcLGOmIBNbWetRg7IP0vdhVgkVwSoZBJeQwY2zhROsJq/HJ+q6tp1qhl9L1+ccC9ZjKs1wV5bmA9NoAWQiZ+7MpzQVq+j74rJQljdVyBdI/dGOvsnBSCxCVW0ISWX0vn9lYTuuHSoaxwCGylH9xRhYHL9bRDskBc7bO0FseHQQasdfghjkl" // "Random"字段的加密数据
}

```

参数      | 说明
-------   | -------------
msg_signature  | 消息体签名
timeStamp | 时间戳
nonce  | 随机字符串
encrypt  | "success"字段的加密字符串


### 3: 获取套件访问Token（suite_access_token）
#### 使用场景

该API用于获取应用套件令牌（suite_access_token）
#### 接口说明

接口调用请求说明
https请求方式: POST
https://oapi.dingtalk.com/service/get_suite_token

POST数据示例

```
{
	"suite_key":"key_value",
 	"suite_secret": "secret_value",
	"suite_ticket": "ticket_value"
}
```

请求参数说明

参数				| 说明
-------			| -------------
suite_key		| 应用套件的key
suite_secret	| 应用套件secret
suite_ticket	| 钉钉后台推送的ticket


返回结果示例

```
{
	"suite_access_token":"61W3mEpU66027wgNZ_MhGHNQDHnFATkDa9-2llqrMBjUwxRSNPbVsMmyD-yq8wZETSoE5NQgecigDrSHkPtIYA", 	"expires_in":7200
}
```

结果参数说明

参数		| 说明
-------	| -------------
suite_access_token	| 应用套件access_token
expires_in			| 有效期


### 4: 获取企业的永久授权码
#### 使用场景

该API用于使用临时授权码换取授权方的永久授权码，并换取授权信息、企业access_token。得到永久授权码之后请将永久授权码存储下来。

注：临时授权码使用一次后即失效
#### 接口说明

接口调用请求说明
https请求方式: POST
https://oapi.dingtalk.com/service/get_permanent_code?suite_access_token=xxxx

POST数据示例

```
{
	"tmp_auth_code": " value"
}
```

请求参数说明

参数		| 说明
-------	| -------------
tmp_auth_code | 回调接口（tmp_auth_code）获取的临时授权码

返回结果示例

```
{
	"permanent_code": "xxxx",
	"auth_corp_info":
	{
		"corpid": "xxxx",
		"corp_name": "name"
    }
}
```

结果参数说明

参数		| 说明
-------	| -------------
permanent_code | 永久授权码
auth_corp_info | 授权方企业信息
corpid | 授权方企业id
corp_name | 授权方企业名称

### 5:获取企业授权的access_token
#### 使用场景

服务提供商在取得企业的永久授权码并完成对企业应用的设置之后，便可以开始通过调用企业接口来运营这些应用。其中，调用企业接口所需的access_token获取方法如下接口说明。
#### 接口说明

接口调用请求说明

https请求方式: POST
https://oapi.dingtalk.com/service/get_corp_token?suite_access_token=xxxx

POST数据示例

```
{
	"auth_corpid": "auth_corpid_value",
	"permanent_code": "code_value"
}
```

请求参数说明

参数		| 说明
-------	| -------------
auth_corpid	| 授权方corpid
permanent_code | 永久授权码，通过get_permanent_code获取

返回结果示例

```
{
	"access_token": "xxxxxx",
	"expires_in": 7200
}
```

结果参数说明

参数 | 说明
-------	| -------------
access_token | 授权方（企业）access_token
expires_in | 授权方（企业）access_token超时时间

### 6: 获取企业授权的授权数据
#### 使用场景

该API用于通过永久授权码换取授权信息。 永久授权码的获取，是通过临时授权码使用get_permanent_code 接口获取到的permanent_code。
#### 接口说明

接口调用请求说明

https请求方式: POST

https://oapi.dingtalk.com/service/get_auth_info?suite_access_token=xxxx

//注意，是suite_access_token，不是授权方（企业）的access_token

POST数据示例

```
{
	"auth_corpid":"auth_corpid_value",
	"permanent_code":"code_value",
	"suite_key":"key_value"
}
```

请求参数说明

参数					| 说明
-------				| -------------
suite_key			| 应用套件key
auth_corpid			| 授权方corpid
permanent_code		| 永久授权码，通过get_permanent_code获取

返回结果示例

```
{
   "auth_corp_info":{
	  "corp_logo_url":"http://xxxx.png",
	  "corp_name":"corpid",
	  "corpid":"auth_corpid_value",
	  "industry":"互联网",
	  "invite_code" : "1001"
	},
	"auth_user_info":
    {
    	"userId":""
	},
    "auth_info":{
	"agent":[{
			"agent_name":"aaaa",
			"agentid":1,
			"appid":-3,
			"logo_url":"http://aaaaaa.com"
	}
	,{
			"agent_name":"bbbb",
			"agentid":4,
			"appid":-2,
			"logo_url":"http://vvvvvv.com"
	}]
	},
		  "errcode":0,
		  "errmsg":"ok"
}
```

结果参数说明

参数					| 说明
-------				| -------------
auth_corp_info		| 授权方企业信息
corpid				| 授权方企业id
invite_code         | 表示邀请码，只有填写过且是ISV自己邀请码的数据才会返回,否则值为空字符串
industry			| 表示企业所属行业
corp_name			| 授权方企业名称
auth_user_info      | 授权方管理员信息
mobile              | 管理员电话
name                | 管理员名字
corp_logo_url		| 企业logo
auth_info			| 授权信息
agent				| 授权的应用信息
agentid				| 授权方应用id
agent_name			| 授权方应用名字
logo_url			| 授权方应用头像
appid				| 服务商套件中的对应应用id


### 7:获取企业的应用信息
#### 使用场景
该API用于获取已授权开通的企业的某个应用的基本信息，包括LOGO,名称，描述等,信息接口调用请求说明
#### 接口说明

https请求方式: POST

https://oapi.dingtalk.com/service/get_agent?suite_access_token=xxxx

POST数据示例

```
{	"suite_key":"key_value",
	"auth_corpid":"auth_corpid_value",
	"permanent_code":"code_value",
	"agentid":541
}
```

请求参数说明

参数					| 说明
-------				| -------------
suite_key			| 应用套件key
auth_corpid			| 授权方corpid
permanent_code		| 永久授权码，从get_permanent_code接口中获取
agentid				| 授权方应用id

返回结果示例

```
{
	"agentid":541,
	"name":"公告",	
	"logo_url":"http://xxxxxxx/png",
	"description":"企业重要消息",
	"close":1,
	"errcode":0,
	"errmsg":"ok"
}
```

结果参数说明

参数			| 说明
-------		| -------------
agentid		| 授权方企业应用id
name		| 授权方企业应用名称
logo_url	| 授权方企业应用头像
description	| 授权方企业应用详情
close		| 授权方企业应用是否被禁用（0:禁用  1:正常  2:待激活 ）

### 8:激活授权套件
#### 使用场景
该API适用于当企业用户授权开通套件时ISV套件进行调用，用于激活授权方企业的套件微应用。如果ISV未调用此接口，则企业用户无法使用ISV套件
#### 接口说明
信息接口调用请求说明

https请求方式: POST

https://oapi.dingtalk.com/service/activate_suite?suite_access_token=xxxx

POST数据示例

```
{
	"suite_key":"key_value",
	"auth_corpid":"auth_corpid_value",
	"permanent_code":"permanent_code"
}
```

请求参数说明

参数				| 说明
-------			| -------------
suite_key		| 应用套件key
auth_corpid		| 授权方corpid
permanent_code	| 永久授权码，从get_permanent_code接口中获取

返回结果示例

```
{
	"errcode":0,
	"errmsg":"ok"
}
```
### 9: 解除授权套件
#### 使用场景

当ISV想重新模拟测试企业发起授权套件，需要先进行解除对套件的授权。

#### 操作说明

解除授权需要进入进入测试企业OA后台--微应用进行操作，如图：

![deleteSuite](https://img.alicdn.com/tps/TB1GpUAKVXXXXckaXXXXXXXXXXX-858-302.jpg)


### 10: ISV为授权方的企业单独设置IP白名单
#### 使用场景

该API用于ISV为企业独立部署场景，在ISV为企业进行独立部署软件系统时，由于是独立机房环境，每套系统是不同的IP地址，ISV可以通过此API为授权套件企业设置IP白名单,设置成功后，套件中的微应用可以调用钉钉开放平台接口服务。
#### 接口说明

https请求方式: POST

https://oapi.dingtalk.com/service/set_corp_ipwhitelist?suite_access_token=xxxx

POST数据示例

```
{	
	"auth_corpid":"dingabcdefgxxx",
	"ip_whitelist":["1.2.3.4","5.6.*.*"]
}
```

请求参数说明

参数					| 说明
-------				| -------------
auth_corpid			| 授权方corpid
ip_whitelist		| 要为其设置的IP白名单,格式支持IP段,用星号表示,如【5.6.\*.\*】,代表从【5.6.0.\*】到【5.6.255.\*】的任意IP,在第三段设为星号时,将忽略第四段的值,注意:仅支持后两段设置为星号

返回结果示例

```
{
	"errcode":0,
	"errmsg":"ok"
}
```
### 消息体签名

为了验证调用者的合法性，钉钉在回调url中增加了消息签名，以参数signature标识，企业需要验证此参数的正确性后再解密。

验证步骤：

1.  企业计算签名：dev_msg_signature=sha1(sort(token、timestamp、nonce、msg_encrypt))。sort的含义是将参数按照字母字典排序，然后从小到大拼接成一个字符串

2. 比较dev_msg_signature和回调接口中推送的字段signature是否相等，相等则表示验证通过


##### 加解密方案说明

开启回调模式时，有以下术语需要了解：

1. signature是签名，用于验证调用者的合法性。具体算法见以下'消息体签名'章节

2. EncodingAESKey：注册套件提供的数据加密密钥。用于消息体的加密，长度固定为43个字符，从a-z, A-Z, 0-9共62个字符中选取，是AESKey的Base64编码。解码后即为32字节长的AESKey

3. AESKey=Base64_Decode(EncodingAESKey + “=”)，是AES算法的密钥，长度为32字节。AES采用CBC模式，数据采用PKCS#7填充；IV初始向量大小为16字节，取AESKey前16字节。具体详见：http://tools.ietf.org/html/rfc2315

4. msg为消息体明文，格式为JSON

5. 钉钉服务器会把msg消息体明文编码成encrypt，encrypt = Base64_Encode(AES_Encrypt[random(16B) + msg_len(4B) + msg + $key])，是对明文消息msg加密处理后的Base64编码。其中random为16字节的随机字符串；msg_len为4字节的msg长度，网络字节序；msg为消息体明文；$key对于ISV开发来说，填写对应的suitekey，$key对于普通企业开发，填写企业的Corpid。
最终传给回调者的是encrypt，字段名为encrypt。

######	对明文msg加密的过程如下：

msg_encrypt = Base64_Encode( AES_Encrypt[random(16B) + msg_len(4B) + msg + $key] )
AES加密的buf由16个字节的随机字符串、4个字节的msg长度、明文msg和$key组成。其中msg_len为msg的字节数，网络字节序；

* $key对于ISV来说，填写对应的suitekey
* $key对于普通企业开发，填写企业的Corpid

##### 对应于加密方案，解密方案如下：

* 取出返回的JSON中的encrypt字段。
* 对密文BASE64解码：aes_msg=Base64_Decode(encrypt)
* 使用AESKey做AES解密：rand_msg=AES_Decrypt(aes_msg)
* 验证解密后$key、msg_len
* 去掉rand_msg头部的16个随机字节，4个字节的msg_len,和尾部的$CorpID即为最终的消息体原文msg

### 加解密库和demo下载
#### Java库和demo
首先，您需要做以下准备工作

1.请开发者使用jdk1.6或以上版本，针对加解密包中使用的org.apache.commons.codec.binary.Base64，须导入jar包commons-codec-1.10(或comm ons-codec-1.9等其他版本)，在java-demo的WebContent/WEB_INF/lib目录中我们也提供了commons-codec-1.10.jar。

官方下载地址：[http://commons.apache.org/proper/commons-codec/download_codec.cgi](http://commons.apache.org/proper/commons-codec/download_codec.cgi)

2.异常java.security.InvalidKeyException:illegal Key Size和『计算解密文字错误』的解决方案：

在官方网站下载JCE无限制权限策略文件
JDK6的下载地址：[http://www.oracle.com/technetwork/java/javase/downloads/jce-6-download-429243.html](http://www.oracle.com/technetwork/java/javase/downloads/jce-6-download-429243.html)

JDK7的下载地址：[http://www.oracle.com/technetwork/java/javase/downloads/jce-7-download-432124.html](http://www.oracle.com/technetwork/java/javase/downloads/jce-7-download-432124.html)

下载后解压，可以看到local_policy.jar和US_export_policy.jar以及readme.txt。如果安装的是JRE，将两个jar文件放到%JRE_HOME% \lib\security目录下覆盖原来的文件，如果安装的是JDK，将两个jar文件放到%JDK_HOME%\jre\lib\security目录下覆盖原来文件。

库地址：[https://github.com/injekt/openapi-demo-java/tree/master/src/com/alibaba/dingtalk/openapi/demo/utils/aes](https://github.com/injekt/openapi-demo-java/tree/master/src/com/alibaba/dingtalk/openapi/demo/utils/aes)

demo地址：[https://github.com/injekt/openapi-demo-java/blob/master/src/com/alibaba/dingtalk/openapi/servlet](https://github.com/injekt/openapi-demo-java/blob/master/src/com/alibaba/dingtalk/openapi/servlet)

#### php库和demo
库地址：[https://github.com/injekt/openapi-demo-php/tree/master/crypto](https://github.com/injekt/openapi-demo-php/tree/master/crypto)

demo地址：[https://github.com/injekt/openapi-demo-php/blob/master/receive.php](https://github.com/injekt/openapi-demo-php/blob/master/receive.php)

#### C#库和demo
库地址：[https://github.com/ian-cuc/suite-demo-c-/tree/master/API](https://github.com/ian-cuc/suite-demo-c-/tree/master/API)

demo地址：[https://github.com/ian-cuc/suite-demo-c-/blob/master/receive.ashx.cs](https://github.com/ian-cuc/suite-demo-c-/blob/master/receive.ashx.cs)

###调试工具

回调接口本地调试方案：由于回调接口需要在外网环境接收钉钉服务器的推送，假如开发者暂时没有外网地址，需要在本地调试回调接口的加解密方案，可以在本地环境构造推送。具体构造参数示例：

URL后面带的参数：signature=5a65ceeef9aab2d149439f82dc191dd6c5cbe2c0&timestamp=1445827045067&nonce=nEXhMP4r

Post参数：
```
{"encrypt":"1a3NBxmCFwkCJvfoQ7WhJHB+iX3qHPsc9JbaDznE1i03peOk1LaOQoRz3+nlyGNhwmwJ3vDMG+OzrHMeiZI7gTRWVdUBmfxjZ8Ej23JVYa9VrYeJ5as7XM/ZpulX8NEQis44w53h1qAgnC3PRzM7Zc/D6Ibr0rgUathB6zRHP8PYrfgnNOS9PhSBdHlegK+AGGanfwjXuQ9+0pZcy0w9lQ=="
}
```
Token：123456

数据加密密钥(ENCODING_AES_KEY)：4g5j64qlyl3zvetqxz5jiocdr586fn2zvjpa8zls3ij

suitekey：suite4xxxxxxxxxxxxxxx


ISV接入相关接口调试：[<font color=red >ISV接入调试工具</font>](https://debug.dingtalk.com/isv.html)

## 套件上架操作流程
### 1. 云市场介绍 

- 1.1 背景介绍

钉钉应用当前依托云市场提供商品管理、交易管理的能力，为钉钉企业提供应用必须通过云市场进行商品相关的操作。

- 1.2 概念定义

名称 | 说明 
------ | ----- 
服务商 | 云市场中的卖家，提供钉钉应用
服务商入驻 | 申请成为云市场卖家的过程，需要填写信息并审核
保证金 | 在云市场的卖家需要缴纳一定金额的保证金，保障服务水平和商品质量
市场 | 云市场将商品进行管理、展示、交易
商品 | 在云市场中进行售卖的应用
商品类型 | 对商品的划分，影响商品展示属性和生产过程，当前只需关注钉钉类商品
商品接入 | 部分商品由云市场进行生产，因此需要先将商品的生产信息提交到云市场进行接入
订单 | 通过订单来完成商品购买的过程
业务 | 订单生成的订单实例即业务，通过业务完成商品生产和交付的过程
云市场API | 云市场生产时可以调用服务商提供的API，服务商完成一定的生产工作后返回结果给云市场

- 1.2 整体流程
![wholeProcess](https://img.alicdn.com/tps/TB10Q8lLXXXXXbaaXXXXXXXXXXX-826-1279.png)

### 2.如何入驻云市场 

入驻云市场您需要完成以下步骤 申请入驻 -> 补充供应商资料 -> 提交店铺资料 -> 支付保证金

- 2.1 申请入驻

您可以通过[<font color=red>申请入驻</font>](http://market.aliyun.com/supplierApply)

- 2.2 补充供应商资料

入驻成功后，您可以访问[<font color=red>服务商平台</font>](http://msp.aliyun.com/)进行操作。
请在左侧菜单中点击”服务商信息”，进入服务商信息维护页面。
[<font color=red>注意，供应商名称、淘宝账号、支付宝账号填写后无法修改，请慎重填写！淘宝账号、支付宝账号必须是关联关系</font>]

- 2.3 提交店铺资料


------ | ----- 

保证金需按照上述表格中的规定进行缴纳。

开户银行： 招商银行杭州分行高新支行

开户名称： 阿里云计算有限公司

帐号： 5719 0549 3610 900


- 3.1 提交商品审核

1.请在发布商品页面选择钉钉类商品。

a)商品名称：请填写您的商品名称，此信息将作为商品名称直接展示给客户。





![submitProduct1](https://img.alicdn.com/tps/TB1A_XoLXXXXXXZaXXXXXXXXXXX-865-363.png)
![submitProduct2](https://img.alicdn.com/tps/TB1lTduLXXXXXakXVXXXXXXXXXX-865-396.png)
![submitProduct3](https://img.alicdn.com/tps/TB1gE4sLXXXXXbrXVXXXXXXXXXX-865-199.png)





![submitProductBiz](https://img.alicdn.com/tps/TB1PMNHLXXXXXb8XpXXXXXXXXXX-865-210.png)

a)商品所属类目：请填写您将商品放在哪个类目下，此选项会影响用户搜索商品时在哪个类目下进行展现。同时，当您选择类目后，系统会显示该类目的商品特有的一些属性，您可以根据实际情况填写属性信息，如果您的商品不包含该属性也可以不进行填写。


5.填写钉钉类商品的销售信息。
![submitProductSel2](https://img.alicdn.com/tps/TB1cbFjLXXXXXcSaXXXXXXXXXXX-844-303.png)
a)售卖方式：钉钉类商品支持按次售卖或按周期售卖。




如果您的钉钉类商品需要版本对应的Sku Code，请提交商品信息后，在商品列表页面点击”管理”。进入商品详情页面后，点击”销售信息”tab，在下图位置可以查看版本对应的Sku Code。
<img src="https://img.alicdn.com/tps/TB1Ts0RLXXXXXbgXXXXXXXXXXXX-865-460.png"  alt="图片名称" align=right />

- 3.2 查看商品

您可以在[<font color=red>服务商平台</font>](http://msp.aliyun.com/commodity/manage/index)左侧菜单中商品管理查看您的商品。
您可以通过商品的上架状态和审核状态对商品进行筛选，并且可以通过列表进入商品详情页面进行商品管理。
![viewProduct](https://img.alicdn.com/tps/TB1R44FLXXXXXc1XpXXXXXXXXXX-865-284.png)


提交商品后，小二会针对商品进行审核。

您的商品审核通过上架后，您可以在商品详情页面编辑商品信息。
![updateProduct](https://img.alicdn.com/tps/TB1y4FVLXXXXXXfXXXXXXXXXXXX-865-179.png)
切换不同的tab页面，点击”编辑”按钮进入编辑状态。

如果您的商品已经上架，需要进行下架，请联系小二进行操作。
### 4. 如何进行交易管理

您可以在[<font color=red>服务商平台</font>](http://msp.aliyun.com/order/order_list.htm)左侧菜单中交易管理-订单管理查看订单信息
![orderManage](https://img.alicdn.com/tps/TB1wvXFLXXXXXc8XpXXXXXXXXXX-465-387.png)

您可以通过订单ID、客户ID、订单状态等条件查询订单。在”操作”栏，点击”查看”可以查看订单详细信息。
![orderManage1](https://img.alicdn.com/tps/TB1fI4yLXXXXXc_XFXXXXXXXXXX-865-396.png)

在订单还未支付前，可以点击”订单改价”修改订单的支付价格。在支付价格中填入金额，填写修改原因，点击”提交”，可以将订单的支付价格修改为您填写的金额。
![orderManage2](https://img.alicdn.com/tps/TB1GetsLXXXXXbJXVXXXXXXXXXX-865-257.png)
在订单支付后，可以点击”关联业务”查看订单生成的业务实例。您也可以从业务管理菜单中直接查看业务信息。

- 4.2 业务管理

您可以在[<font color=red>服务商平台</font>](http://msp.aliyun.com/orderbiz/order_biz_list.htm)左侧菜单中交易管理-业务管理查看业务信息
![bizManage](https://img.alicdn.com/tps/TB1eUhwLXXXXXXQXVXXXXXXXXXX-865-376.png)
您可以通过业务ID、客户ID、业务状态等条件查询业务。在”操作”栏，点击”查看”可以查看业务详细信息。





您可以在[<font color=red>服务商平台</font>](http://msp.aliyun.com/refund/refund_record_list.htm)左侧菜单中交易管理-退款管理查看退款信息。
![refundManage](https://img.alicdn.com/tps/TB1zoJJLXXXXXaeXpXXXXXXXXXX-865-250.png)






您可以通过客户ID、商品名称、回复状态等条件查询用户回复。

### 5. 如何生产商品
------ | ----- 
- 5.1 ISV接入API

接口调试工具：http://msp.aliyun.com/isvDoc  ISV需要使用用MSP的帐号登陆进行调试

### 6. 线下操作

- 6.1 结算收款
### 7.  用户授权

当企业管理员通过云市场完成套件购买后，通过钉钉授权功能进行钉钉套件授权开通，具体授权开通流程见：
[<font color=red >企业管理员授权应用</font>](#企业管理员授权应用)

##  ISV通用技术方案

### ISV套件对企业独立部署方案
#### 背景：
#### 系统实现：












![system_design](https://img.alicdn.com/tps/TB1TgCgLXXXXXXqXVXXXXXXXXXX-802-514.png)

### ISV用户账号绑定方案

#### 背景：

1，只存在于ISV系统中的用户

2，只存在于钉钉系统中的用户

3，在钉钉与ISV系统中同时存在的用户
#### 概述：
#### 系统实现：
1，只存在于ISV系统中的用户：

 通过邀请码注册的企业可以调用钉钉开放平台的通讯录接口，具有通讯录维护的权限，通过接口直接同步企业组织结构及人员信息到钉钉

1.1 有手机号码：

通过钉钉开放平台接口同步企业及用户数据，ISV系统采用钉钉userid进行账号绑定

1.2 有邮箱：

采用快速部署方式，企业创建成功后通过钉钉接口获取加入团队链接，邮件通知企业员工进行加入，ISV系统采用钉钉userid进行账号绑定

2，只存在于钉钉系统中的用户：

ISV在企业授权时通过钉钉接口获取组织结构与人员信息，通过钉钉userid与ISV用户信息进行关联实现绑定

3，在钉钉与ISV系统中同时存在的用户：

ISV需以钉钉通讯录为准进行账号同步与绑定，与只存在于钉钉系统中的用户采用相同的处理方式，产品上可以实现让用户显示绑定已有ISV系统账号，通过免登获取钉钉userid进行系统账号绑定