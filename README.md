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




## Description

## Setting
以下のように接続しています。

データのやり取りはI2Cで、電源は3.3Vです。

