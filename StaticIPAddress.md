# 固定 IP Address の設定
## OS : Ubuntu Server 24.04 LTS (64-bit) 

### netplan による IP Address の指定
+ Ubuntu では netplan というツールを利用する.
+ /etc/netplan/ の下の YAML ファイル (.yaml) で行う.
+ 初期設定ファイル : 50-cloud-init.yaml
+ YAML ファイルは複数設置可能で, 数値によって適用順序を設定可能.

### 今回実施した作業
1. カレントディレクトリを移動
  + cd /etc/netplan
2. 初期設定のYAMLファイルを別名で保存
  + sudo mv 50-cloud-init.yaml 50-cloud-init.yaml.org
3. 自分用の設定ファイル（01-rpi-net-config.yaml）を設置
  + sudo nano 01-rpi-net-config.yaml
```yaml
# Raspberry pi 3 で k8s を構築する環境のYAMLファイル
network:
  version: 2
  renderer: networkd
  ethernets:
    eth0:
      dhcp4: no     # dhcpは使用しない
      addresses: [192.168.xxx.xxx/24]   # 独自のネットワークIPを個別に設定
      gateway4: 192.168.xxx.yyy         # デフォルトゲートウェイ
      nameservers:
        addresses: [192.168.xxx.yyy, 8.8.8.8, 8.8.4.4]
        # ↑ DNSサーバのIPアドレス（←はGoogleのDNSサーバー）
```
※ インデントはタブではなくスペースで記述する. 

### 補足
+ Raspberry Pi OS (Raspbian) では, かつて /etc/network/interfaces で設定していた.
+ 現在は /etc/dhcpcd.conf を利用するらしい．
+ しかし, ネットなどで調べた資料にしたがって設定しても固定 IP アドレスで動作してくれない.
+ dhcpcd がインストールされていなかったり, インストールして起動するように設定したり... となんだか細かい作業が多い.
+ 今回の実験では Ubuntu Server を利用することにしたので, このメモの作業内容を実行した.
