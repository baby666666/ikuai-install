# iKuai 3.7.21 Enterprise WireGuard 分流版

本仓库提供 iKuai 3.7.21 x64 Enterprise + Shell 完整功能 + WireGuard 出口 WAN 分流修改版。

## 主要功能

- WireGuard 服务接口支持绑定指定 WAN。
- WireGuard 接入流量支持源进源出，避免从默认 WAN 出口返回。
- WireGuard 客户端配置支持生成、复制和二维码。
- WireGuard 默认参数已优化，方便连续新增接口和隧道。
- Web 版本升级包会保留 WireGuard 修改，不重新加密 rootfs。

## 全新安装

适合重装服务器或新机器直接安装。

```bash
curl -O https://raw.githubusercontent.com/bin456789/reinstall/main/reinstall.sh && bash reinstall.sh dd --img https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise-ShellFull-WG-WAN-Hook_Build202509221910_eth0-wan1-wanweb.img.gz
```

镜像 SHA256：

```text
87c0a5113323b4615faa306849868048c17116aab0046e2bd2e6eb4c2888e2c8
```

## Web 升级

适合已经安装 iKuai 3.7.21 x64 Enterprise 的机器，在 Web 后台升级到 WireGuard 分流版。

升级包下载：

```text
https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise-ShellFull-WG-WAN-Hook_Build202509221910.bin
```

升级包 SHA256：

```text
23638b7292570f4798a4b8dbafd60ce17e558008587171fd33667a90320d8f0d
```

升级路径：

```text
系统设置 > 升级备份 > 版本升级 > 手动升级 > 选择文件 > 上传文件
```

说明：

- 该 `.bin` 使用系统升级包格式，Web“版本升级”可识别。
- 上传解析/升级时会先写入 `/etc/mnt/deve.sh` 和 `/etc/log/script/install.sh`，再按系统升级流程写入第 1 分区。
- 不重新加密 rootfs，避免因 rootfs 重打包导致无限重启。
- 升级完成后建议重启一次，并清理浏览器缓存后再进入 WireGuard 页面。

## WireGuard 使用建议

新增 WireGuard 接口后，在“线路”里选择需要绑定的 WAN。  
如果路由器下的设备需要走 WireGuard，在“流控分流 > 分流设置 > 端口分流”里选择对应 WireGuard 线路。

## 其他保留包

原版 Enterprise 升级包：

```text
https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise.bin
```

全部文件校验值见：

```text
https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/SHA256SUMS
```
