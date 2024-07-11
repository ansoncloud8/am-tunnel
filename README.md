# AmTunnel
# Cloudflare Workers 和 Pages 生成节点订阅

这是一个基于 Cloudflare Workers 和 Pages平台的脚本，在原版的基础上修改了显示 VLESS 配置信息转换为订阅内容。使用该脚本，你可以方便地将 VLESS、trojan 配置信息使用在线配置转换到 Clash、 Singbox 、Quantumult X等工具中。

- 基础部署视频教程：[小白教程](https://www.youtube.com/watch?v=f9hDJCqAEGA) 小白必看 一步到胃 最佳推荐!!!
- 快速部署视频教程：[详细教程](https://www.youtube.com/watch?v=XS0EgqckUKo) ***最佳推荐!!!***
- 进阶使用视频教程：[进阶教程](https://www.youtube.com/watch?v=JDAQYD6bvEM) 折腾自己的优选IP
- 高级使用视频教程：[高级教程](https://www.youtube.com/watch?v=lQ2Evd_xPRY) 成为折腾的高手

- AM科技官网：[https://am.809098.xyz](官网)
- YouTube：[https://youtube.com/@AM_CLUB](AM科技)
- Telegram：[https://t.me/AM_CLUBS](AM_CLUBS)
- Github：[https://github.com/ansoncloud8](ansoncloud8)
- VLESS订阅信息：[节点订阅信息](https://worker.amcloud.filegear-sg.me/866853eb-5293-4f09-bf00-e13eb237c655)


# 免责声明

本免责声明适用于 GitHub 上的 “am-tunnel” 项目（以下简称“该项目”），项目链接为：https://github.com/ansoncloud8/am-tunnel

### 用途
该项目被设计和开发仅供学习、研究和安全测试目的。它旨在为安全研究者、学术界人士和技术爱好者提供一个了解和实践网络通信技术的工具。

### 合法性
使用者在下载和使用该项目时，必须遵守当地法律和规定。使用者有责任确保他们的行为符合其所在地区的法律、规章以及其他适用的规定。

### 免责
1. 作为该项目的作者，我（以下简称“作者”）强调该项目应仅用于合法、道德和教育目的。
2. 作者不鼓励、不支持也不促进任何形式的非法使用该项目。如果发现该项目被用于非法或不道德的活动，作者将强烈谴责这种行为。
3. 作者对任何人或团体使用该项目进行的任何非法活动不承担责任。使用者使用该项目时产生的任何后果由使用者本人承担。
4. 作者不对使用该项目可能引起的任何直接或间接损害负责。
5. 通过使用该项目，使用者表示理解并同意本免责声明的所有条款。如果使用者不同意这些条款，应立即停止使用该项目。

作者保留随时更新本免责声明的权利，且不另行通知。最新的免责声明版本将会在该项目的 GitHub 页面上发布。

## 风险提示
- 通过提交虚假的节点配置给订阅服务，避免节点配置信息泄露。


## Workers 部署方法 [视频教程](https://www.youtube.com/watch?v=f9hDJCqAEGA)
1. 部署 Cloudflare Worker：
   - 在 Cloudflare Worker 控制台中创建一个新的 Worker。
   - 将 [worker.js](https://github.com/ansoncloud8/am-tunnel/blob/dev/_worker.js) 的内容粘贴到 Worker 编辑器中。
   - 将第 6 行 `userID` 修改成你自己的 **UUID** 。
2. 访问订阅内容：
   - 访问 `https://[YOUR-WORKERS-URL]/[UUID]` 即可获取订阅内容。
   - 例如 `https://vless.google.workers.dev/90cd4a77-141a-43c9-991b-08263cfe9c10` 就是你的通用自适应订阅地址。
   - 例如 `https://vless.google.workers.dev/sub/90cd4a77-141a-43c9-991b-08263cfe9c10` Base64订阅格式，适用PassWall,SSR+等。
   - 例如 `https://vless.google.workers.dev/sub/90cd4a77-141a-43c9-991b-08263cfe9c10?format=clash` Clash订阅格式，适用OpenClash等。
   - 例如 `https://vless.google.workers.dev/sub/bestip/90cd4a77-141a-43c9-991b-08263cfe9c10?format=singbox&uuid=68ecf7d9-5eb3-31ee-fe78-134a3d519356` singbox订阅格式，适用singbox等。
   - 例如 `https://vless.google.workers.dev/sub/bestip/90cd4a77-141a-43c9-991b-08263cfe9c10?format=qx&uuid=68ecf7d9-5eb3-31ee-fe78-134a3d519356` Quantumult X订阅格式，适用Quantumult X工具。
3. 给 workers绑定 自定义域： 
   - 在 workers控制台的 `触发器`选项卡，下方点击 `添加自定义域`。
   - 填入你已转入 CloudFlare 域名解析服务的次级域名，例如:`vless.google.com`后 点击`添加自定义域`，等待证书生效即可。

</details>

## Pages 上传 部署方法 **最佳推荐!!!** [视频教程](https://www.youtube.com/watch?v=8oZvklBkMj4)
1. 部署 Cloudflare Pages：
   - 下载 [_worker.js.zip](https://raw.githubusercontent.com/ansoncloud8/am-tunnel/dev/_worker.js.zip) 文件，并点上 Star !!!
   - 在 Cloudflare Pages 控制台中选择 `上传资产`后，为你的项目取名后点击 `创建项目`，然后上传你下载好的 [_worker.js.zip](https://raw.githubusercontent.com/ansoncloud8/am-tunnel/dev/_worker.js.zip) 文件后点击 `部署站点`。
   - 部署完成后点击 `继续处理站点` 后，选择 `设置` > `环境变量` > **制作**为生产环境定义变量 > `添加变量`。
     变量名称填写**UUID**，值则为你的UUID，后点击 `保存`即可。
   - 返回 `部署` 选项卡，在右下角点击 `创建新部署` 后，重新上传 [_worker.js.zip](https://raw.githubusercontent.com/ansoncloud8/am-tunnel/dev/_worker.js.zip) 文件后点击 `保存并部署` 即可。
2. 访问订阅内容：
   - 访问 `https://[YOUR-PAGES-URL]/[YOUR-UUID]` 即可获取订阅内容。
   - 例如 `https://vless.google.pages.dev/90cd4a77-141a-43c9-991b-08263cfe9c10` 就是你的通用自适应订阅地址。
   - 例如 `https://vless.google.pages.dev/sub/90cd4a77-141a-43c9-991b-08263cfe9c10` Base64订阅格式，适用PassWall,SSR+等。
   - 例如 `https://vless.google.pages.dev/sub/90cd4a77-141a-43c9-991b-08263cfe9c10?format=clash` Clash订阅格式，适用OpenClash等。
   - 例如 `https://vless.google.pages.dev/sub/bestip/90cd4a77-141a-43c9-991b-08263cfe9c10?format=singbox&uuid=68ecf7d9-5eb3-31ee-fe78-134a3d519356` singbox订阅格式，适用singbox等。
   - 例如 `https://vless.google.pages.dev/sub/bestip/90cd4a77-141a-43c9-991b-08263cfe9c10?format=qx&uuid=68ecf7d9-5eb3-31ee-fe78-134a3d519356` Quantumult X订阅格式，适用Quantumult X工具。


3. 给 Pages绑定 CNAME自定义域：[视频教程](https://www.youtube.com/watch?v=8oZvklBkMj4)
   - 在 Pages控制台的 `自定义域`选项卡，下方点击 `设置自定义域`。
   - 填入你的自定义次级域名，注意不要使用你的根域名，例如：
     您分配到的域名是 `google.com`，则添加自定义域填入 `vless.google.com`即可；
   - 按照 Cloudflare 的要求将返回你的域名DNS服务商，添加 该自定义域 `vless`的 CNAME记录 `vless.google.pages.dev` 后，点击 `激活域`即可。

</details>

## Pages GitHub 部署方法 
1. 部署 Cloudflare Pages：
   - 在 Github 上先 Fork 本项目，并点上 Star !!!
   - 在 Cloudflare Pages 控制台中选择 `连接到 Git`后，选中 `am-tunnel`项目后点击 `开始设置`。
   - 在 `设置构建和部署`页面下方，选择 `环境变量（高级）`后并 `添加变量`
     变量名称填写**UUID**，值则为你的UUID，后点击 `保存并部署`即可。

2. 访问订阅内容：
   - 访问 `https://[YOUR-PAGES-URL]/[YOUR-UUID]` 即可获取订阅内容。
   - 例如 `https://vless.google.pages.dev/90cd4a77-141a-43c9-991b-08263cfe9c10` 就是你的通用自适应订阅地址。
   - 例如 `https://vless.google.pages.dev/sub/90cd4a77-141a-43c9-991b-08263cfe9c10` Base64订阅格式，适用PassWall,SSR+等。
   - 例如 `https://vless.google.pages.dev/sub/90cd4a77-141a-43c9-991b-08263cfe9c10?format=clash` Clash订阅格式，适用OpenClash等。
   - 例如 `https://vless.google.pages.dev/sub/bestip/90cd4a77-141a-43c9-991b-08263cfe9c10?format=singbox&uuid=68ecf7d9-5eb3-31ee-fe78-134a3d519356` singbox订阅格式，适用singbox等。
   - 例如 `https://vless.google.pages.dev/sub/bestip/90cd4a77-141a-43c9-991b-08263cfe9c10?format=qx&uuid=68ecf7d9-5eb3-31ee-fe78-134a3d519356` Quantumult X订阅格式，适用Quantumult X工具。

3. 给 Pages绑定 CNAME自定义域：[视频教程](https://www.youtube.com/watch?v=8oZvklBkMj4)
   - 在 Pages控制台的 `自定义域`选项卡，下方点击 `设置自定义域`。
   - 填入你的自定义次级域名，注意不要使用你的根域名，例如：
     您分配到的域名是 `google.com`，则添加自定义域填入 `vless.google.com`即可；
   - 按照 Cloudflare 的要求将返回你的域名DNS服务商，添加 该自定义域 `vless`的 CNAME记录 `vless.google.pages.dev` 后，点击 `激活域`即可。


</details>

## 变量说明
| 变量名 | 示例 | 必填 | 备注 | YT |  |
|--------|---------|-|-----|-----|--------|
| UUID | 90cd4a77-141a-43c9-991b-08263cfe9c10 |√| Powershell -NoExit -Command "[guid]::NewGuid()"| [Video](https://www.youtube.com/watch?v=8oZvklBkMj4) |  |
| PROXYIP | ts.hpc.tw |×| 备选作为访问CloudFlareCDN站点的代理节点(支持多ProxyIP, ProxyIP之间使用`,`或 换行 作间隔) | [Video](https://youtu.be/CiSdaNOCyOk) |  |
| ADDRESSESAPI | https://raw.githubusercontent.com/ansoncloud8/am-tunnel/dev/ipv4.txt |×| 备选作为优选IP的自己库) | [Video](https://youtu.be/9WoMNrxV0HE) |  |


## Star 星星走起
[![Stargazers over time](https://starchart.cc/ansoncloud8/am-tunnel.svg?variant=adaptive)](https://starchart.cc/ansoncloud8/am-tunnel)

## 已适配自适应订阅内容
   - [v2rayN](https://github.com/2dust/v2rayN)
   - [v2rayU](https://github.com/yanue/V2rayU/releases)
   - [sing-box](https://github.com/SagerNet/sing-box)
   - clash.meta（[clash-verge-rev
](https://github.com/clash-verge-rev/clash-verge-rev)，[Clash Nyanpasu](https://github.com/keiko233/clash-nyanpasu)，~[clash-verge](https://github.com/zzzgydi/clash-verge/tree/main)~，ClashX Meta、openclash）
   - Quantumult X
   - 小火箭
   - surge
  

# 感谢
[3Kmfi6HP](https://github.com/3Kmfi6HP/EDtunnel)、[ACL4SSR](https://github.com/ACL4SSR/ACL4SSR/tree/master/Clash/config)、[肥羊订阅转换](https://suburl.v1.mk)

