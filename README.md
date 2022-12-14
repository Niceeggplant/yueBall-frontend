# 移动端后台管理系统 RuoYi-Mobile
主页：<a href="http://fastbuild.run" target="_blank">http://fastbuild.run</a> 

[![gitee star](https://gitee.com/yinm/RuoYi-Mobile/badge/star.svg?theme=dark)]('https://gitee.com/yinm/RuoYi-Mobile/stargazers')
[![gitee fork](https://gitee.com/yinm/RuoYi-Mobile/badge/fork.svg?theme=dark)]('https://gitee.com/yinm/RuoYi-Mobile/members')
[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)

# 非常抱歉！最近公司项目较忙，项目疏于维护，预计11月中下旬回归！
# 在此期间欢迎大家PR，增加完善功能，我会定期合并。
# 另外，有技术过硬的，有意愿做私活的小伙伴，可将做过的项目、开源的地址、居住城市、擅长方向、可接受工作时段等等信息，发送邮件至fastbuild@163.com。

### :peach: 项目简介
企事业单位信息化加速，移动端办工逐渐成为趋势，H5或小程序比起APP来说更简单方便。因此一款好的移动端基础平台十分有必要。<br>
项目采用当下流行的UniApp + uView2 框架开发，完成常见的日常工作功能与移动端特有功能组件。
<br><br>

### :pear: 后端下载
下载地址：<a href="http://fastbuild.run" target="_blank">传送门</a><br>
***注：目前移动端支持若依管理平台全系列（单应用、微服务、MySQL版、Oracle版、SqlServer版、Antd版等），需要适配其他版本的请到上面地址下载移动端源码。***
<br><br>

###  :strawberry: 扫码预览
<table>
    <tr>
        <td valign="top" width="180"><img src="https://images.gitee.com/uploads/images/2022/0526/091635_6bfffb01_1203341.png"/></td>
        <td valign="center" align="center" width="180">尚未发布</td>
        <td valign="center" align="center" width="180">尚未发布</td>
        <td valign="center" align="center" width="180">尚未发布</td>
    </tr>
    <tr>
        <td valign="top" align="center">H5</td>
        <td valign="top" align="center">微信小程序</td>
        <td valign="top" align="center">支付宝小程序</td>
        <td valign="top" align="center">其他</td>
    </tr>
</table>
<br><br>

###  :watermelon:  技术栈
| 组件       | 版本     |
|----------|--------|
| uview-ui | 2.0.31 |
| qiun-data-charts | 2.4.3-20220505 |

<br><br>

###   :tw-1f348:   系统配置
1. 后端请求地址配置：

```
# 配置文件路径：/config/environment.js
# 修改baseURL属性

const environment = {
	// 开发环境配置
	development: {
		// 本地部署的后端
		baseURL: 'http://localhost:8080',
		
		// 直接使用线上后端
		// baseURL: 'http://vue.ruoyi.vip/prod-api'
	},
	// 生产环境配置
	production: {
		baseURL: 'http://vue.ruoyi.vip/prod-api' // 发布时需要修改为后端实际地址
	}
}

module.exports = {
  environment: environment[process.env.NODE_ENV]
}
```
2. H5启动端口配置：

***注意：不要在manifest.json中配置h5启动信息，可能会引发后端接口访问异常***

```
# 配置文件路径：/vue.config.js
# 修改port属性

const { environment } = require('./config/environment.js')

module.exports = {
  devServer: {
    port: 9001,
    proxy: {
      '/': {
        target: environment.baseURL,
        ws: true,
        changeOrigin: true,
        pathRewrite: {
          '^/': ''
        }
      }
    },
  }
}

```




###    :lemon:   系统截图
<table>
    <tr>
        <td valign="top"><img src="https://gitee.com/yinm/RuoYi-Mobile/raw/master/static/preview/login.jpg"/></td>
        <td valign="top"><img src="https://gitee.com/yinm/RuoYi-Mobile/raw/master/static/preview/index.jpg"/></td>
        <td valign="top"><img src="https://gitee.com/yinm/RuoYi-Mobile/raw/master/static/preview/work.jpg"/></td>
        <td valign="top"><img src="https://gitee.com/yinm/RuoYi-Mobile/raw/master/static/preview/my.jpg"/></td>
    </tr>
    <tr>
        <td valign="top"><img src="https://gitee.com/yinm/RuoYi-Mobile/raw/master/static/preview/notice-m.jpg"/></td>
        <td valign="top"><img src="https://gitee.com/yinm/RuoYi-Mobile/raw/master/static/preview/notice-e.jpg"/></td>
        <td valign="top"><img src="https://gitee.com/yinm/RuoYi-Mobile/raw/master/static/preview/prefile.jpg"/></td>
        <td valign="top"><img src="https://gitee.com/yinm/RuoYi-Mobile/raw/master/static/preview/pwd-reset.jpg"/></td>
    </tr>
</table>
<br><br>

###  :lollipop: 技术交流
QQ群：860974500

<br><br>
#### 如果觉得项目还不错，一定记得 :star: 一下
#### 如果觉得项目还不错，一定记得 :star: 一下
#### 如果觉得项目还不错，一定记得 :star: 一下
<br><br>

###  :poultry_leg:  给作者加个鸡腿
如果对您的工作或学习产生些许帮助，可以给作者的午餐加一个鸡腿 :poultry_leg:  :poultry_leg:  :poultry_leg: ！~~
<table>
    <tr>
        <td valign="top" width="180"><img src="https://gitee.com/yinm/RuoYi-Mobile/raw/master/static/preview/wechat_pay.jpg"/></td>
        <td valign="top" width="180"><img src="https://gitee.com/yinm/RuoYi-Mobile/raw/master/static/preview/ali_pay.jpg"/></td>
    </tr>
    <tr>
        <td valign="top" align="center">微信捐助</td>
        <td valign="top" align="center">支付宝捐助</td>
    </tr>
</table>