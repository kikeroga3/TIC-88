<b>Build Raspberry Pi TIC-80</b>

<pre>
sudo apt update
sudo apt dist-upgrade

sudo apt install --reinstall libraspberrypi0 libraspberrypi-dev libraspberrypi-bin
sudo apt install build-essential libgtk-3-dev libsdl2-dev zlib1g-dev liblua5.3-dev libgif-dev
sudo apt install git cmake lxshortcut
sudo apt install raspberrypi-kernel-headers

sudo cp /opt/vc/lib/libbcm_host.so /usr/local/lib

git clone --recursive https://github.com/nesbox/TIC-80
cd TIC-80/build
cmake ..
make
</pre>

<b>Create shortcut on desktop</b>

<pre>
lxshortcut -o ~/Desktop/TIC-80
</pre>

<b>Enable OpenGL</b>

<pre>
sudo raspi-config
</pre>

Enable "Advanced Options" -> "GL Drivers" -> "GL (Fake KMS) Desktop Driver" and restart the OS.

-- 日本語 --

<b>★ラズパイ版TIC-80のビルド</b>

ラズパイ起動後、ターミナルから以下コマンドを実行

・Rasbian Busterの環境を最新化
<pre>
sudo apt update
sudo apt dist-upgrade
</pre>
・必要なライブラリをインストール
<pre>
sudo apt install --reinstall libraspberrypi0 libraspberrypi-dev libraspberrypi-bin
sudo apt install build-essential libgtk-3-dev libsdl2-dev zlib1g-dev liblua5.3-dev libgif-dev
sudo apt install git cmake lxshortcut
sudo apt install raspberrypi-kernel-headers
sudo cp /opt/vc/lib/libbcm_host.so /usr/local/lib
</pre>
・TIC-80ソースファイルをダウンロードしてビルド
<pre>
git clone --recursive https://github.com/nesbox/TIC-80
cd TIC-80/build
cmake ..
make
</pre>
「bin」配下に実行ファイル"tic80"が生成される

・ショートカット作成
<pre>
lxshortcut -o ~/Desktop/TIC-80
</pre>
・OpenGL有効化
<pre>
sudo raspi-config
</pre>
「Advanced Options」->「GL Drivers」->「GL (Fake KMS) Desktop Driver」を有効化し、OS再起動。
