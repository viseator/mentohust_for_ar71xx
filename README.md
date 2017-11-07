# 用于AR71xx系列的mentohust

注意先要安装官方源中的`libpcap`（`openwrt`本身应处于联网状态）：

```bash
opkg update
opkg install libpcap
```

再安装`libsodium_1.0.12-1_ar71xx.ipk`：

```bash
opkg install libsodium_1.0.12-1_ar71xx.ipk
```

再安装`mentohust`：

```bash
opkg install mentohust_0.3.1-1_ar71xx.ipk
```

注意必须进行`mentohust`可执行文件的替换，否则会出现`can't resolve symbol 'atexit' in lib`错误：

```bash
chmod a+x mentohust
cp mentohust /usr/sbin
```

安装`luci`界面：

```bash
opkg install luci-app-mentohust_trunk+svn-1_ar71xx.ipk 
```

之后使用时一定要选对网卡，打开`luci`界面的`enable`。
