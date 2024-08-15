# Raspberry Pi の初期設定
## OS : Ubuntu Server 24.04 LTS(64-bit)

### 準備したマシン
+ Raspberry Pi 3 Model B
+ Raspberry Pi 4 Model B

### 準備した　OS
+ Ubuntu Server 24.04 LTS (64-bit)
+ ↑ 2024年08月現在での最新

### 補足
+ Raspberry Pi 3 で GUI デスクトップを動かすと動作が重い.
+ Raspberry Pi 4 で Raspberry Pi OS のデスクトップは一応使えそうだが, Ubuntu Desktop だとまだ動作が重いと感じた.
+ 実験内容でやりたい設定が Ubuntu の方が良さそうなので， とりあえず Server を入れて, GUI デスクトップが欲しかったら何か軽量なデスクトップを後からみつくろって入れる.

### OS の準備と更新
1. sudo apt update            # 更新データの取得
2. sudo apt upgrade -y        # アップグレード(現状の依存関係は維持)
3. sudo apt full-upgrade -y   # 全体的なアップグレード（依存関係の再構築も含む）
4. sudo apt autoremove        # 不要なパッケージの削除
5. sudo apt autoclean         # 不要なキャッシュの削除

※ Raspberry Pi OS で full-upgrade を実行すると， デスクトップがデビアンの物に勝手に変わる場合があった.
※ ネットの記事でも上記の現象があったりするから, よくわからない人はしないほうがいい... といった記事もあった.
※ ↑ 見た目の変更方法などもネット上にはあるから, 自力で色々変更したり戻したりできるならいいけど, 面倒ではある.
※ 現状では GUI デスクトップ使ってないし, 特別なアプリとか開発環境とか入れてないからとりあえず full-upgrade やっとく. 
