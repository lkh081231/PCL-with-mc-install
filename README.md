# Plain Craft Launcher (解除 MC 下载限制版)

> [!TIP]
> **关于本仓库**：本仓库 Fork 自官方 [Meloong-Git/PCL](https://github.com/Meloong-Git/PCL)，通过改动源码 (*ps:具体方式为避免给原作者惹麻烦就不说了，想知道自己问ai去吧 (⌒▽⌒)*)  **解除了 Minecraft 本体及整合包的下载限制**。
> 
> 本仓库配置了 GitHub Actions 自动工作流，每当上游仓库更新时会自动同步最新代码、验证解除限制是否有效，并将编译打包好的可执行程序（`.zip` 压缩包，解压即可直接运行）自动发布到本仓库的 **[Releases](https://github.com/lkh081231/PCL-with-mc-intstall/releases)** 页面。
> 
> 👉 **[点击前往 Releases 页面直接下载最新版本](https://github.com/lkh081231/PCL-with-mc-intstall/releases/latest)**

### ⚠️ 与官网闭源正式版的功能差异 / 限制说明

由于原仓库在开源时移除了部分私有密钥与闭源服务端鉴权代码，从本仓库 Releases 下载的开源编译版与官网闭源版相比存在以下差异：

1. **微软正版账号新增登录（等待 Mojang 审核中）**：微软 OAuth 登录所需的 `Client ID` 已经申请并内置到程序中，**目前正版登录功能正在等待 Mojang 审核**，审核通过后即可直接使用（离线登录和第三方外置登录如 LittleSkin / 统一通行证不受影响）。在此之前如需使用，也可在运行电脑上自行设置系统环境变量 `PCL_MS_CLIENT_ID`。
2. **CurseForge 资源检索与下载（已支持 ✅）**：已申请并配置内置了 `CURSEFORGE_API_KEY`，CurseForge 与 Modrinth 资源均可直接正常搜索与下载。
3. **大厅联机功能（不可用）**：联机模块依赖 PCL 官方闭源服务端的配置鉴权下发，开源版无法获取该配置。
4. **启动器本体在线更新（已移除）**：开源版移除了连接官方更新服务器的逻辑（这也正好避免了启动器自动更新回被限制下载的官方版本）。
5. **赞助解锁主题 & 百宝箱（已移除）**：隐藏主题的解锁校验算法、识别码生成及早期调试百宝箱未在开源仓库中公开（默认主题及基础 UI 设置仍可正常使用）。
6. **注册表配置隔离 & 启动弹窗提示（行为差异）**：
   - 每次启动时会弹出一次“开源版本说明”提示框。
   - 全局注册表配置存储在 `HKEY_CURRENT_USER\Software\PCLDebug`（官方版为 `PCL`），因此不会自动读取旧版保存在注册表中的全局设置（游戏目录内的 `PCL\Setup.ini` 配置不受影响）。

---

[![Stars](https://img.shields.io/github/stars/Meloong-Git/PCL?style=flat&logo=data:image/svg%2bxml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZlcnNpb249IjEiIHdpZHRoPSIxNiIgaGVpZ2h0PSIxNiI+PHBhdGggZD0iTTggLjI1YS43NS43NSAwIDAgMSAuNjczLjQxOGwxLjg4MiAzLjgxNSA0LjIxLjYxMmEuNzUuNzUgMCAwIDEgLjQxNiAxLjI3OWwtMy4wNDYgMi45Ny43MTkgNC4xOTJhLjc1MS43NTEgMCAwIDEtMS4wODguNzkxTDggMTIuMzQ3bC0zLjc2NiAxLjk4YS43NS43NSAwIDAgMS0xLjA4OC0uNzlsLjcyLTQuMTk0TC44MTggNi4zNzRhLjc1Ljc1IDAgMCAxIC40MTYtMS4yOGw0LjIxLS42MTFMNy4zMjcuNjY4QS43NS43NSAwIDAgMSA4IC4yNVoiIGZpbGw9IiNlYWM1NGYiLz48L3N2Zz4=&logoSize=auto&label=Stars&labelColor=444444&color=eac54f)](https://github.com/Meloong-Git/PCL/)
[![Issues](https://img.shields.io/github/issues/Meloong-Git/PCL?style=flat&label=Issues&labelColor=444444&color=1F883D)](https://github.com/Meloong-Git/PCL/issues)
[![哔哩哔哩](https://img.shields.io/badge/动态-BiliBili-00A4DB?style=flat&labelColor=444444&logoSize=auto)](https://space.bilibili.com/11343203/dynamic)
[![爱发电](https://img.shields.io/badge/赞助-爱发电-946ce6?style=flat&labelColor=444444&logoSize=auto)](https://meloong.com/afd/a/LTCat)

包含 PCL 的大部分源代码，包括 UI 库、动画模块、下载模块、Minecraft 启动模块等！<br/>
代码并不是实时更新的，它会在每次 PCL 发布更新时同步一次。<br/>
非常感谢社区的大力支持！

>上面显示的star 不是我的，是原仓库的:(

<br/>

### 相关资源
- [PCL 下载（原版）](https://meloong.com/pcl)：下载可免费使用的正式版 PCL！解除限制版👉[点击前往 Releases 页面直接下载最新版本](https://github.com/lkh081231/PCL-with-mc-intstall/releases/latest)
- [PCL 功能投票](https://github.com/Meloong-Git/PCL/discussions/2)：来参加投票吧，开发者会优先处理票数较高的项目！
- [帮助文档库](https://github.com/LTCatt/PCL2Help)：PCL 内置帮助文档的存储库
