# �g����
git clone ���đS�t�@�C������Ă����� 7zip �� 001.zip ���𓀂��Ă��������B

# ���ꂽ�h���C�o
- https://vibsdepot.v-front.de/wiki/index.php/Net55-r8168 (RTL8111�Ƃ�)
�t�@�C����: net55-r8168-8.045a-napi.x86_64.vib
- https://flings.vmware.com/usb-network-native-driver-for-esxi?download_url=https%3A%2F%2Fdownload3.vmware.com%2Fsoftware%2Fvmw-tools%2FUSBNND%2FESXi670-VMKUSB-NIC-FLING-24524132-offline_bundle-13958648.zip (USB-NIC)a
�t�@�C����: VMW_bootbank_vmkusb-nic-fling_1.10-1vmw.703.0.50.55634242.vib
- https://flings.vmware.com/community-networking-driver-for-esxi (IntelNUC����,1.2.7)
�t�@�C����: VMW_bootbank_net-community_1.2.7.0-1vmw.700.1.0.15843807.vib

# �ǂ�����č��ꂽ��
PowerCLI ���� ESXi-Cusomizer-PS-v2.8.1.ps1 ���ȉ��`���Ŏ��s

```
cd <��L�h���C�o��vib���܂Ƃ߂��f�B���N�g��>
.\ESXi-Customizer-PS-v2.8.1.ps1 -v70 -pkgDir .\ -NSC
```

## ESXi-Customizer-PS-v.2.8.1.ps1 �͈ȉ��������

https://github.com/VFrontDe-Org/ESXi-Customizer-PS/blob/b2ac47c41a866a08b1e94158c79828b08eeaa116/ESXi-Customizer-PS.ps1

�����������ŐV��2.9.0�A������PowerCLI 6.5.0 �Ƃ��ݍ���Ȃ��̂����܂�������
