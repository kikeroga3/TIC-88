★ラズパイ版TIC-80のビルド

ラズパイ起動後、ターミナルから以下コマンドを実行

・Rasbian Busterの環境を最新化

sudo apt update
sudo apt dist-upgrade

・必要なライブラリをインストール

sudo apt install --reinstall libraspberrypi0 libraspberrypi-dev libraspberrypi-bin
sudo apt install build-essential libgtk-3-dev libsdl2-dev zlib1g-dev liblua5.3-dev libgif-dev
sudo apt install git cmake lxshortcut
sudo apt install raspberrypi-kernel-headers
sudo cp /opt/vc/lib/libbcm_host.so /usr/local/lib

・TIC-80ソースファイルをダウンロードしてビルド

git clone --recursive https://github.com/nesbox/TIC-80
cd TIC-80/build
cmake ..
make

「bin」配下に実行ファイル"tic80"が生成される

・ショートカット作成

lxshortcut -o ~/Desktop/TIC-80

・OpenGL有効化

sudo raspi-config

「Advanced Options」->「GL Drivers」->「GL (Fake KMS) Desktop Driver」を有効化し、OS再起動。

