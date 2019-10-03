# Getting Start

## ファームウェアをダウンロードする

[ファームウェアのリリースページ](https://github.com/hatanoh/qmk_firmware/releases/tag/bmp-0.2.0-20191001300)からダウンロードします

対応するブートローダのバージョンが書かれていますので、確認します。

## (必要に応じて)ブートローダを書き込む
前のステップで、確認した対応ブートローダがまだ書き込まれていない場合は、置き換える必要があります。

[ブートローダダウンロードページ](https://github.com/sekigon-gonnoc/BLE-Micro-Pro/releases)から対応するブートローダをダウンロードします

[BLE Micro ProのGettingStart](https://github.com/sekigon-gonnoc/BLE-Micro-Pro/blob/master/AboutDefaultFirmware/doc/getting_start.md)に従ってブートローダを書き込みます

## ファームウェアを書き込む
DFUで起動します。リセットボタンを押しながらUSBで接続します。

新しいブートローダが書き込まれていれば BLEMICROPRO ドライブが見えます。

![Drive UF2](https://github.com/hatanoh/BMPCommonFirmware/raw/master/Doc/picture/BMP_DFU.PNG)

中にはINDEX.HTMとINFO_UF2.TXTがあり、INFO_UF2.TXTの中に書かれたバージョンが期待したバージョンであることを確認します。
```
UF2 Bootloader x.x.x-bmp-xxxxxxxx
Model: BLE Micro Pro
Board-ID: NRF52840-BMP-V1
API version: 3
Config version: 2
```
ダウンロードしていたファームウェアで拡張子 .uf2 の物をドライブにコピーします。

ファームのアップデートが終わるとBMPは再起動し、一度ドライブが切断されます。

再起動のあと再度ドライブを開くと中身が増えています

![Drive Firmware](https://github.com/hatanoh/BMPCommonFirmware/raw/master/Doc/picture/BMP_FIRM.PNG)

中のVERSION.TXTを開き期待したバージョンであることを確認します。
```
API version: 3
Config version: 2
Build from xxxxxxxxxx
Build Target: sarasarado_ble_default
```

## ファイルを書き込む
コンフィグファイルなどは、レポジトリの[keyboards/sarasarado_ble/config](https://github.com/hatanoh/qmk_firmware/tree/dev/ble_micro_pro/keyboards/sarasarado_ble/config)にあります。

まず、キーボード名のフォルダの下のCONFIG.JSN(分割キーボードの場合はCONFIG_MASTER.JSN(左側)/CONFIG_SLAVE.JSN(右側))をBLEMICROPROドライブにコピーします。

コピーが終わったらBMPを再起動します。

コピーが終わったら、KEYMAP.JSN / TAPTERM.JSNをコピーするとキーボードとして機能するようになります。

ペアリングして使いましょう。
