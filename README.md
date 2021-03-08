# SurveillanceCamera

概要
監視カメラです。カメラとサーモグラフィカメラで動体検知を行い、検知したら警告音とLine経由でスマホに通知します。
このような外形になります。配線などの見た目の雑さはありますが、とりあえず機能面に問題はないので...

[参考サイト](https://dream-soft.mydns.jp/blog/developper/smarthome/2020/01/649/)

## 使用モジュール
ラズベリーパイ4 コンピューターモデルB 4GB 
[Raspberry Pi Camera Module V2 ラズベリーパイ カメラ ソニーIMX219PQ CMOS画像センサ](https://www.amazon.co.jp/%E3%83%A9%E3%82%BA%E3%83%99%E3%83%AA%E3%83%BC%E3%83%91%E3%82%A44-%E3%82%B3%E3%83%B3%E3%83%94%E3%83%A5%E3%83%BC%E3%82%BF%E3%83%BC%E3%83%A2%E3%83%87%E3%83%ABB-Raspberry-Computer-Model/dp/B07WR5W2D6/ref=sr_1_1_sspa?dchild=1&hvadid=490228284849&hvdev=c&jp-ad-ap=0&keywords=raspberry+pi+4+model+b%2F2gb&qid=1615233376&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEzQk9WOEU4T1k1VE5ZJmVuY3J5cHRlZElkPUEwMTAyNjYzRElFU0daT0RUOEsxJmVuY3J5cHRlZEFkSWQ9QTFKM1hFWjRVU0k5QTImd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl) 
[AMG8833](https://www.switch-science.com/catalog/3395/) 
[Akozon ビープ音アラームセンサーモジュール](https://www.amazon.co.jp/gp/product/B07NR6SNQZ/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1)



[参考にしたサイト](https://ambidata.io/samples/m5stack/thermalcamera/)


## Description
M5stackには3つのボタンがあり、一番左のボタンを押すとモード0、真ん中のボタンを押すとモード1、一番右のボタンを押すとモード2としています。  
各モードの機能・使い方は以下のとおりです。

### モード0
サーモグラフィーの動作確認用に実装しました。  
下画像のように、温度が表示されれば正常です。  
[モード0の画面](https://user-images.githubusercontent.com/78978860/107856827-464f6b80-6e6e-11eb-9fbb-7d27006dd593.JPG)

### モード1
監視カメラのようなものです。  
温度変化が一定以上になった場合、人が入ったと検知します。  
[モード1の画面](https://user-images.githubusercontent.com/78978860/107857239-96c7c880-6e70-11eb-9e97-64d282f1b169.JPG)

指をサーモグラフィーの視野内で動かすと「detect」と表示されることが確認できます。  
[人を検知したときの画面](https://user-images.githubusercontent.com/78978860/107857562-43567a00-6e72-11eb-9a26-394ba4e90693.JPG)  
本来は「detect」の表示だけでなく、音を鳴らしたり、スマホに通知が来るようにしたほうがいいですが、そこまでは作りこんでいません。

モード1になっている状態で、もう一度真ん中のボタンを押すと、感度が変化しますので調節可能です。

### モード2
非接触体温計のようなものです。
最初に温度計測しておいて、それ以上であれば体温上昇していると判断します。  
[モード2の画面](https://user-images.githubusercontent.com/78978860/107857608-aba55b80-6e72-11eb-8953-dd99aee11b8d.JPG)

モード2になっている状態で、もう一度一番右のボタンを押すと、体温計測ができます。  
平熱や計測部位はヒトによって異なると思うので、最初の体温計測を基準とします。  
2回目以降は1回目の体温より低ければ何も表示せず、高ければした画像のように「Be Careful」と表示します。  
[上昇検知時の画面](https://user-images.githubusercontent.com/78978860/107857707-633a6d80-6e73-11eb-8642-f113414ded07.JPG)

サーモグラフィー AMG8833の温度精度がTyp.±2.5℃なので、あまり信頼できません。
あくまで参考程度にでも。


## Setting
以下のように接続しています。
[ピン構成](https://user-images.githubusercontent.com/78978860/107857884-8ca7c900-6e74-11eb-95c9-3d9127dcc5f1.PNG)  
データのやり取りはI2Cで、電源は3.3Vです。

