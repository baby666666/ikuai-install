# iKuai img.gz 云服务器安装

## 一键安装

```bash
wget https://raw.githubusercontent.com/baby666666/ikuai-install/main/install-ikuai.sh && chmod +x install-ikuai.sh && ./install-ikuai.sh
```

## 直接使用 img.gz

64 位：

```bash
curl -O https://raw.githubusercontent.com/bin456789/reinstall/main/reinstall.sh && bash reinstall.sh dd --img https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.19_Build202504071142_eth0-wan1-wanweb.img.gz
```

32 位：

```bash
curl -O https://raw.githubusercontent.com/bin456789/reinstall/main/reinstall.sh && bash reinstall.sh dd --img https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x32_3.7.19_Build202504071142_eth0-wan1-wanweb.img.gz
```

64 位 Enterprise 3.7.21：

```bash
curl -O https://raw.githubusercontent.com/bin456789/reinstall/main/reinstall.sh && bash reinstall.sh dd --img https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise_Build202509221910_eth0-wan1-wanweb.img.gz
```

64 位 Shell 3.7.21：

```bash
curl -O https://raw.githubusercontent.com/bin456789/reinstall/main/reinstall.sh && bash reinstall.sh dd --img https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Build202508211345-shell_eth0-wan1-wanweb.img.gz
```

64 位 Enterprise 3.7.21 + Shell 完整功能：

```bash
curl -O https://raw.githubusercontent.com/bin456789/reinstall/main/reinstall.sh && bash reinstall.sh dd --img https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise-ShellFull_Build202509221910_eth0-wan1-wanweb.img.gz
```

64 位 Enterprise 3.7.21 + Shell 完整功能 + WireGuard 出口 WAN 分流 + 智能 DNS 分流：

```bash
curl -O https://raw.githubusercontent.com/bin456789/reinstall/main/reinstall.sh && bash reinstall.sh dd --img https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise-ShellFull-WG-DNS-Test_Build202509221921_eth0-wan1-wanweb.img.gz
```

保留 WireGuard 功能的 Web 版本升级包：

```text
https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise-ShellFull-WG-DNS-Test_Build202509221921.bin
```

这个 `.bin` 使用 `firmwareid=10001`，Web“版本升级”可识别。上传解析/升级时会先写入 `/etc/mnt/deve.sh` 和 `/etc/log/script/install.sh`，再按系统升级流程写入第 1 分区；不重新加密 rootfs。升级包不修改现有网口绑定，原来 `eth0` 绑定什么就保持什么。

中国大陆 IP 库自动更新已接入 Web，位置：`网络设置 > 终端分组设置 > IP分组设置` 页面底部的“中国IP库自动更新”，默认写入 IP 分组 `china_auto`。B 节点中心分流仍在 `流控分流 > 分流设置 > 端口分流` 页面底部，大陆/海外出口线路从真实线路下拉选择，支持 WAN、PPTP、L2TP、OpenVPN、IKEv2 和 WireGuard，并优先使用 `china_auto` 作为大陆目标库。也可以继续用脚本测试：

```bash
/usr/ikuai/script/wg_center_route.sh update_apply
```

64 位 Enterprise 3.7.21 + Shell 完整功能 EFI 引导版：

```bash
curl -O https://raw.githubusercontent.com/bin456789/reinstall/main/reinstall.sh && bash reinstall.sh dd --img https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise-ShellFull-EFI_Build202509221910_eth0-wan1-wanweb.img.gz
```

64 位 Enterprise 3.7.21 + Shell 完整功能升级包：

```bash
https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise.bin
```

镜像已预设 `eth0 -> wan1`，并开启 WAN 口 Web 访问。
