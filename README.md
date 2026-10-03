# iKuai 交流群
镜像来自 [ikuai交流群](https://t.me/ikuai8)

本仓库仅提供 **iKuai 3.7.26 免费插件版 IMG.GZ 一键安装镜像**及校验文件。镜像来自 [ikuai-free](https://github.com/baby666666/ikuai-free/releases/tag/v3.7.26-free-plugins)，基于官方 x64 免费版 Build202609111743，加入插件管理；属于**非官方定制固件**。

**安装会清空目标系统磁盘上的系统、配置和数据。执行前请阅读[免责声明](DISCLAIMER.md)，备份数据，并确认有云控制台或其它恢复手段。**

## 下载

- [免费插件版 IMG.GZ](https://github.com/baby666666/ikuai-install/releases/download/v3.7.26-free-install/iKuai8_x64_3.7.26_Free_Plugins_EFI_eth0-WAN-Web.img.gz)
- [SHA256SUMS](https://github.com/baby666666/ikuai-install/releases/download/v3.7.26-free-install/SHA256SUMS)

镜像 SHA256：`d84c1080a19c4ced87ee863d74e255afbc1f80f3f58d41b6df4f1186abe357a6`。

本镜像与 ikuai-free 发布文件逐字节一致。本仓库不提供企业版或单独的 Web 升级 BIN；IMG.GZ 不能上传到爱快 Web 升级页面。

## 一键安装

在需要重装的 **x86_64 Linux** 服务器上，以 **root** 身份执行：

```bash
curl -fL https://raw.githubusercontent.com/bin456789/reinstall/main/reinstall.sh -o reinstall.sh && bash reinstall.sh dd --img https://github.com/baby666666/ikuai-install/releases/download/v3.7.26-free-install/iKuai8_x64_3.7.26_Free_Plugins_EFI_eth0-WAN-Web.img.gz
```

命令下载并执行 [bin456789/reinstall](https://github.com/bin456789/reinstall) 上游脚本，使用本仓库免费版镜像重装。准备完成后按脚本提示重启；救援环境需联网下载镜像。脚本跟随上游 main 更新，执行前应自行查看下载的脚本内容和上游使用要求。

## 默认配置与使用条件

- x86_64，保留 BIOS / UEFI 引导结构；不包含 Secure Boot，使用 EFI 时需关闭 Secure Boot。
- 默认 `eth0 → wan1`，DHCP 获取地址，开启 WAN Web。静态 IP、特殊 VLAN、/32 或特殊网关需通过控制台另行配置。
- 默认账号和密码为 `admin / admin`。首次登录立即修改密码，并通过云安全组或防火墙限制管理来源。
- 首次初始化后，正常重启不再覆盖用户网络设置。安装前保留云控制台或串口/VNC 入口。

硬件、云网络、存储和引导兼容性以实际环境为准。具体已完成的测试见来源仓库的[验证记录](https://github.com/baby666666/ikuai-free/blob/main/docs/VALIDATION.md)，不将企业版测试结论用于本镜像。

## 校验与源码

下载镜像及 SHA256SUMS 到同一目录，执行：

```bash
sha256sum -c SHA256SUMS
```

macOS 使用 `shasum -a 256 -c SHA256SUMS`。校验用于确认下载完整性，不能替代对镜像、插件或安装脚本的安全审查。

完整源码、构建输入和复现方法见 [ikuai-free](https://github.com/baby666666/ikuai-free) 及其[复现教程](https://github.com/baby666666/ikuai-free/blob/main/docs/REPRODUCE.md)。权利归属及使用风险见[免责声明](DISCLAIMER.md)。
