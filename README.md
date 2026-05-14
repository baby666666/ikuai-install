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

64 位 Enterprise 3.7.21 + Shell 完整功能 EFI 引导版：

```bash
curl -O https://raw.githubusercontent.com/bin456789/reinstall/main/reinstall.sh && bash reinstall.sh dd --img https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise-ShellFull-EFI_Build202509221910_eth0-wan1-wanweb.img.gz
```

64 位 Enterprise 3.7.21 + Shell 完整功能升级包：

```bash
https://raw.githubusercontent.com/baby666666/ikuai-install/main/iso/iKuai8_x64_3.7.21_Enterprise.bin
```

镜像已预设 `eth0 -> wan1`，并开启 WAN 口 Web 访问。
