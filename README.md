# RaspberryPI-pico 1st Step

## 構築環境
* エディション	Windows 11 Pro
* バージョン	22H2
* OS ビルド	22621.1555
* エクスペリエンス	Windows Feature Experience Pack 1000.22640.1000.0
* 11th Gen Intel(R) Core(TM) i5-11500 @ 2.70GHz 2.71 GHz
* (WSL2) Ubuntu22.04

## 下準備
### APTリポジトリの追加
```
sudo add-apt-repository universe multiverse restricted
```
### VSCODEリポジトリの追加
```
curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo install -o root -g root -m 644 microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list
```
### ライブラリの事前インストール　※重複あるかもしれませんが念のため
```
sudo apt install libusb-dev libusb-1.0-0-dev libssl-dev pkg-config
```
### 最新版CMakeのインストール(git clone)　※APT標準でいいかもしれませんが念のため
```
git clone https://github.com/Kitware/CMake.git
cd CMake/
./bootstrap
make
sudo make install
```
## 公式設定手順の実行
[Getting started with Raspberry Pi Pico](https://datasheets.raspberrypi.com/pico/getting-started-with-pico.pdf)

Chapter 1. Quick Pico Setupの内容のみ
```
wget https://raw.githubusercontent.com/raspberrypi/pico-setup/master/pico_setup.sh
chmod +x pico_setup.sh
./pico_setup.sh
```

> sudo: raspi-config: command not found

が最後に出ますが、Raspberry PIに導入した場合に有効な項目なので気にしない。。
