此文档简要介绍演示代码的结构和使用方式

### 部署与配置
1. 确保PHP版本不低于7.0；安装composer依赖
1. 复制一份`config.example.php`文件到`config.php`，并根据需要修改配置内容
1. 将程序部署到任意服务器上，需保证`example`目录下的文件可访问，`cache`目录可读写
1. 在微信公众平台`开发 > 基本配置`中配置`IP白名单`为服务器IP

### 公众平台测试号
如果你没有已认证的公众号用于测试，可以去微信官网[申请测试号](https://mp.weixin.qq.com/debug/cgi-bin/sandbox?t=sandbox/login)，测试号拥有绝大部分接口权限

### 文件说明
- **cache/** - 示例中缓存文件目录
- **config.example.php** - 配置示例文件
- **Cache.php** - Cache类实现示例
- **init.php** - 初始化文件，用于实例化`WeChat`类，被其它文件引用
- **model.php** - 演示如何调用微信接口，浏览器直接访问此文件即可
- **notify.php** - 消息通知的基本演示。配置流程:
  - 在公众平台`开发 > 基本配置 > 服务器配置`中填写`notify.php`的访问地址，地址需外网可访问
  - 配置Token、EncodingAESKey等参数与`config.php`中一致，点击提交即可

  配置完成后即可进入公众号测试 _文本消息、图片消息、关注公众号、场景值二维码和地理位置_ 等通知消息
- **oauth.php** - 微信网页授权，微信客户端中访问即可授权获得用户信息。_需要在公众平台`开发 > 接口权限 > 网页服务 > 网页帐号 > 网页授权获取用户基本信息`中修改授权回调域名为访问域名_
- **jssdk.php** - 演示JS-SDK初始化，微信客户端中访问即可。_公众平台`公众号设置 > 功能设置`中需要将`JS接口安全域名`配置为访问域名_