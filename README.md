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

64 位 Enterprise 3.7.21 + Shell 完整功能 + WireGuard 出口 WAN 分流：

```bash
curl -O https://raw.githubusercontent.com/bin456789/reinstall/main/reinstall.sh && bash reinstall.sh dd --img https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise-ShellFull-WG-WAN-Hook_Build202509221910_eth0-wan1-wanweb.img.gz
```

保留 WireGuard 功能的 Web 版本升级包：

```text
https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise-ShellFull-WG-WAN-Hook_Build202509221910.bin
```

这个 `.bin` 使用 `firmwareid=10001`，Web“版本升级”可识别。上传解析/升级时会先写入 `/etc/mnt/deve.sh` 和 `/etc/log/script/install.sh`，再按系统升级流程写入第 1 分区；不重新加密 rootfs。升级包不修改现有网口绑定，原来 `eth0` 绑定什么就保持什么。

B 节点中心分流测试脚本会安装到 `/usr/ikuai/script/wg_center_route.sh`，默认关闭。需要在 B 上编辑 `/etc/mnt/ikuai/wg_center.conf`，把 `ENABLE=1`、`CLIENT_SRC`、`CHINA_IFACE`、`OVERSEA_IFACE` 改成实际网段和 WireGuard 接口后执行：

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
