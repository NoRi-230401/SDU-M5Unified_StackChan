# SDU-M5Unified_StackChan

SD-Updaterに対応したスタックチャン独り言（MP3ファイル）ソフトです。<br>
<br>

@mongonta555 さんのソフトから次の修正を行いました。<br>

- SD-Updater対応。
- サーボOn/Off、PIN番号の設定を外部ファイル（servo.txt）で設定。
- volumeの値を外部ファイル（volume.txt）で指定。
- 立上げ時のbeepを消音。

ブート時に、SD_Updater用の画面が立ち上がります。<br>
SDに入れたソフトを切り替えることができるようになります。<br>
<br>



## 設定ファイル
SD直下に置いてください。

- servo.txt<br>
１行目(SERVO_ON_OFF)： "on" または、 "off"<br>
２行目(SERVO_PIN_X) ： "13"(PortC)　または、"33"(PortA)<br>
３行目(SERVO_PIN_Y) ： "14"(Portc)　または、"32"(PortA)<br>
<br>
設定のサンプルファイルがあります。
名前を"servo.txt"に変更してSD直下にコピーしてください。 <br>
<br>

- volume.txt<br>
１行目(VOLUME_VALUE)： "0" ～ "255"　の数字<br>
ブート時に読み込みます。動作中は固定です。
<br>
<br>

## 必要なもの
### 本体<br>
いずれかを用意してください。<br>
・M5Stack Core2 for AWS<br>
・M5Stack Core2 <br>
・M5Stack Core2 v1.1　（未確認）<br>
<br>

### サーボ
・SG90　または互換<br>
・サーボポートは、PortAまたは、PortC のどちらも対応。<br>
・サーボがなくても顔だけの動作もOKです。設定でサーボOFFも指定できます。<br>
<br>

### SDカード
設定ファイル"servo.txt", "volume.txt"および、 mp3フォルダ下に音声データが必要です。<br>
SDは、いろいろ問題あるようなので、なるべく実績のあるものをご使用ください。<br>
<br><br>


## 最新BINの取得
コンパイル済みの最新BINファイルは、下記のリポジトリから取得できます。
- [BinsPack-for-StackChan-Core2](https://github.com/NoRi-230401/BinsPack-for-StackChan-Core2)<br>
<br>


## SD-Updaterについて
tobozoさん開発。SDに複数のBINファイルを入れて、ソフトを切替えて使用できるようになります。<br>

 https://github.com/tobozo/M5Stack-SD-Updater<br><br>


タカオさん、2023/7/29 ｽﾀｯｸﾁｬﾝ お誕生日会 2023のLTで、M5Stack-SD-Updaterの概要を説明した時のスライド<br>
https://speakerdeck.com/mongonta0716/sutatukutiyandefu-shu-apuriwoqie-riti-erutekunituku

<br><br>

ソフトの操作方法等は、下記ソフトを参照してください。
<br>


## 基のリポジトリ
- [M5Unified_StackChan (mongonta0716さん)](https://github.com/mongonta0716/M5Unified_StackChan)<br>
<br>

- [M5Unified_StackChan (robo8080さん)](https://github.com/robo8080/M5Unified_StackChan)　オリジナル<br>
<br><br>
<br><br>

ここから、基ソフトの説明書です。

-----
# M5Unified_StackChan
独り言を言うｽﾀｯｸﾁｬﾝです。セリフをSDカードにmp3ファイルで入れておくとランダムに再生します。
<br><br>
@mongonta555 さんの[ｽﾀｯｸﾁｬﾝ M5GoBottom版組み立てキット](https://raspberrypi.mongonta.com/about-products-stackchan-m5gobottom-version/ "Title")に対応しています。<br>

Avatar表示は、meganetaaanさんのm5stack-avatarをベースにさせていただきました。<br>
オリジナルはこちら。<br>
An M5Stack library for rendering avatar faces <https://github.com/meganetaaan/m5stack-avator><br>

---

### M5GoBottom版ｽﾀｯｸﾁｬﾝ本体を作るのに必要な物、及び作り方 ###
こちらを参照してください。<br>
* [ｽﾀｯｸﾁｬﾝ M5GoBottom版組み立てキット](https://raspberrypi.mongonta.com/about-products-stackchan-m5gobottom-version/ "Title")<br>

---

### 必要な物 ###
* [M5Stack](http://www.m5stack.com/ "Title") (M5Stack Core2で動作確認しました。)<br>
* VSCode<br>
* PlatformIO<br>

使用しているライブラリ等は"platformio.ini"を参照してください。<br>

---

### サーボモーターを使用するGPIO番号の設定 ###
* M5Unified_StackChan.inoの13行目付近、サーボモーターを使用するGPIO番号を設定してください。<br>

---

### 使い方 ###
* SDカードに、mp3というディレクトリを作りそこにmp3ファイルを入れておきます<br>
* mp3ファイルのサンプリング周波数は16khzか24khzにしてください。<br>
* ファイル名に全角文字や長いファイル名はつかえません。10文字以内で作成してください。<br>
* サンプルのmp3ファイルがmp3ディレクトリに入っています。<br>
* サイズの大きいMP3ファイルを再生すると途切れたり、画面の左端に短い線が表示されることがあります。<br>
この音声データは[「VOICEVOX;ずんだもん」](https://voicevox.hiroshiba.jp/ "Title")を使用して作成しました。<br>
<br><br>
