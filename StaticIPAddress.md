# 固定 IP Address の設定
## OS : Ubuntu Server 24.04 LTS (64-bit) 

### netplan による IP Address の指定
+ Ubuntu では netplan というツールを利用する.
+ /etc/netplan/ の下の YAML ファイル (.yaml) で行う. 

### 補足
+ Raspberry Pi OS (Raspbian) では, かつて /etc/network/interfaces で設定していた.
+ 現在は /etc/dhcpcd.conf を利用するらしい．
+ しかし, ネットなどで調べた資料にしたがって設定しても固定 IP アドレスで動作してくれない.
+ dhcpcd がインストールされていなかったり, インストールして起動するように設定したり... となんだか細かい作業が多い.
+ 今回の実験では Ubuntu Server を利用することにしたので, このメモの作業内容を実行した.
