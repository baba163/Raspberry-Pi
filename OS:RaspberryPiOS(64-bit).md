# Raspberry Pi の OS と初期設定
## OS : Raspberry Pi OS (64-bit)

### 準備したマシン
+ Raspberry Pi 3 Model B
+ Raspberry Pi 4 Model B

### 準備した　OS
+ Raspberry Pi OS (64-bit)
+ ↑ 2024年08月現在での最新
+ Raspberry Pi 3 以降の CPU が 64-bit のマシンでは, 64-bit の OS が利用可能.

### OS の準備と更新
1. sudo apt update            # 更新データの取得
2. sudo apt upgrade -y        # アップグレード(現状の依存関係は維持)
3. sudo apt full-upgrade -y   # 全体的なアップグレード（依存関係の再構築も含む）
4. sudo apt autoremove        # 不要なパッケージの削除
5. sudo apt autoclean         # 不要なキャッシュの削除

+ Raspberry Pi OS で full-upgrade を実行すると， デスクトップがデビアンの物に勝手に変わる場合があった.
+ ネットの記事でも上記の現象があったりするから, よくわからない人はしないほうがいい... といった記事もあった.
+ ↑ 見た目の変更方法などもネット上にはあるから, 自力で色々変更したり戻したりできるならいいけど, 面倒ではある.

### 補足
+ 昔は Raspberry Pi 用にカスタマイズされた Debian を Raspbian と言ってたが, 今は Raspberry Pi OS というみたい. 
+ Raspberry Pi 3 で GUI デスクトップを動かすと動作が重い.
+ Raspberry Pi 4 で Raspberry Pi OS のデスクトップは一応使えそう.
+ 昔は apt-get を使っていたけど, 新しい方法では apt を使う. （よりユーザーに優しい？）
+ 細かい違いはあるので, ヘビーユーザーでこだわった細かい調整が必要な人は apt-get でも良いが, 初心者などは新しい apt の方が推奨（?) 
+ GUI のメニューからロケールを日本にして再起動すれば, とりあえずの日本語化もできる.
+ デスクトップマシンとしての環境設定は昔に比べると随分と楽になった.
  
