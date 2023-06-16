# キャチロボ専用基板　仕様書
## マイコン
- Raspberry Pi Pico W x1

## 使用するアクチュエータ・センサ
- ステッピングモーター x2
- サーボ x3
- フォトリフレクタ x4
- 圧電スピーカー x1

## ピン配置
- GP0~2(サーボ)
- GP3(圧電スピーカー)
- GP6(モータ①step),GP7(モータ①dir)
- GP10(モータ②step),GP11(モータ②dir)
- GP12(遠隔非常停止)
- GP14(アナログマルチプレクサA),GP15(アナログマルチプレクサB)
- GP18~21(DIPスイッチ0-3)
- GP28(センサ読み取り用)

![Raspberry Pi Picoのピン配置](https://image.itmedia.co.jp/news/articles/2107/23/l_bmepico01.jpg)

### アナログマルチプレクサ
アナログマルチプレクサはA,Bの2つの信号で読み取るチャンネルを切り替えられる.以下の表を参照してほしい.
AはGP15,BはGP15に接続されている.
![真理値表](/catchrobo2023/Images/CD4051B_Truth.png)

[CD4051BM96データシート](https://datasheet.lcsc.com/lcsc/1809261612_Texas-Instruments-CD4051BM96_C21379.pdf)

### 

## 回路図（暫定）
以下のファイルに現在の暫定版の回路図がある.
catchrobo2023/catchrobo2023.pdf
![回路図](/catchrobo2023/Images/Circuit.png)
![基板の外形](/catchrobo2023/Images/Substrate.png)