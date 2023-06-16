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
- GP6(モータ①Step),GP7(モータ①Dir)
- GP10(モータ②Step),GP11(モータ②Dir)
- GP12(遠隔非常停止)
- GP14(アナログマルチプレクサA),GP15(アナログマルチプレクサB)
- GP18~21(DIPスイッチ0-3)
- GP28(センサ読み取り用:ADC)

![Raspberry Pi Picoのピン配置](https://image.itmedia.co.jp/news/articles/2107/23/l_bmepico01.jpg)

### MD・ステッピングモーター
使用するMDは[STSPIN220](https://akizukidenshi.com/catalog/g/gK-14790/)であり,
**Dirピン→方向**
**Stepピン→回転**
を指定する.

[17HS16-2004S1データシート](https://www.omc-stepperonline.com/download/17HS16-2004S1.pdf)
[Amazon上でのサイトページ](https://www.amazon.co.jp/Nema-%E3%82%B9%E3%83%86%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%83%A2%E3%83%BC%E3%82%BF-%E3%83%90%E3%82%A4%E3%83%9D%E3%83%BC%E3%83%A91-8%C2%B0-13Ncm-42x42x20mm/dp/B074Y4NP78/ref=asc_df_B074Y4NP78/?tag=jpgo-22&linkCode=df0&hvadid=265845994451&hvpos=&hvnetw=g&hvrand=9291562426356432587&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1009285&hvtargid=pla-456291539009&psc=1)


### アナログマルチプレクサ
アナログマルチプレクサはA,Bの2つの信号で読み取るチャンネルを切り替えられる.以下の真理値表を参照してほしい.
![真理値表](/catchrobo2023/Images/CD4051B_Truth.png)
AはGP15,BはGP15に接続されている.**GP28のADC機能を用いて,チャンネルを切り替えながら周囲の障害物を検知する.**
[CD4051BM96データシート](https://datasheet.lcsc.com/lcsc/1809261612_Texas-Instruments-CD4051BM96_C21379.pdf)

## 回路図（暫定）
以下のファイルに現在の暫定版の回路図がある.
catchrobo2023/catchrobo2023.pdf
![回路図](/catchrobo2023/Images/Circuit.png)
![基板の外形](/catchrobo2023/Images/Substrate.png)