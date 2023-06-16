# 使い方
git clone して全ファイル取ってきたら 7zip で zip.001 を解凍してください。すると ISO が出てきます。

あとは自由に、例えば Rufus で USB メモリにでも書き込んでください。

# 動作確認

## OKパターン
USB メモリで起動してこの画面まで勝手に行くのであればNICは認識されています。

HDD や SSD の中身を書き換える前の段階なので、ここまでならデータが消える心配はないです。

![image](https://github.com/sakkuntyo/ESXi-ISO-70u3m-usbnic-intelnuc-RTL8111/assets/20591351/8a031342-bfec-4cfe-a91b-f1b8adef5d43)

## NGパターン

このメッセージならこの ISO に入れられたドライバでは、その NIC は認識できません。

"No network adapters were detected."

![image](https://github.com/sakkuntyo/ESXi-ISO-70u3m-usbnic-intelnuc-RTL8111/assets/20591351/abb03687-267a-49bf-9b99-36bd237e2968)


# 入れたドライバ
- 1. https://vibsdepot.v-front.de/wiki/index.php/Net55-r8168 
  - ファイル名: net55-r8168-8.045a-napi.x86_64.vib
  - 対応:RTL8111とか
- 2. https://flings.vmware.com/usb-network-native-driver-for-esxi?download_url=https%3A%2F%2Fdownload3.vmware.com%2Fsoftware%2Fvmw-tools%2FUSBNND%2FESXi670-VMKUSB-NIC-FLING-24524132-offline_bundle-13958648.zip
  - ファイル名: VMW_bootbank_vmkusb-nic-fling_1.10-1vmw.703.0.50.55634242.vib
  - 対応: USB NIC
- 3. https://flings.vmware.com/community-networking-driver-for-esxi
  - ファイル名: VMW_bootbank_net-community_1.2.7.0-1vmw.700.1.0.15843807.vib
  - 対応: IntelNUC

# どうやって作られたか
PowerCLI 6.5.0 から ESXi-Cusomizer-PS-v2.8.1.ps1 を以下形式で実行

```
cd <上記ドライバのvibをまとめたディレクトリ>
.\ESXi-Customizer-PS-v2.8.1.ps1 -v70 -pkgDir .\ -NSC
```

## ESXi-Customizer-PS-v.2.8.1.ps1 は以下から入手

https://github.com/VFrontDe-Org/ESXi-Customizer-PS/blob/b2ac47c41a866a08b1e94158c79828b08eeaa116/ESXi-Customizer-PS.ps1

試した当時最新は 2.9.0、2.9.0 は PowerCLI 6.5.0 とかみ合わないのかうまくいかず

# 動作確認した USB NIC

- TP-Link 有線LANアダプタ ギガビット イーサネット Nintendo Switch/windows/Linux/macOS 対応 UE305 (スイッチ用に買ってた)
https://amzn.to/3XiItFx
![image](https://github.com/sakkuntyo/ESXi-ISO-70u3m-usbnic-intelnuc-RTL8111/assets/20591351/f4ecf344-25ef-4504-93fe-213c0f2b2617)

