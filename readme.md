#雑多メモ

##ubuntuのフォルダ名を英語にする

```
LANG=C xdg-user-dirs-gtk-update
```

##git初期設定

```
git config --global user.name "<firstname> <familyname>"
git config --global user.email "<email address>"
```

##uefiを有効化したvirtualbox上のubuntu (他でもそう？)
仮想マシンをシャットダウンした後、bootloader情報が飛ぶみたいなので、無理やり起こす

1. とりま何とか立ち上げる.
2. デフォルトのbootloaderはboot/bootx64.efiで動くようなので、以下のようにbootloaderをコピーしてでっち上げる.

```
sudo su -
cd /boot/efi/EFI
cp -a ubuntu boot
cd boot
mv grubx64.efi bootx64.efi
sync;sync;sync;
reboot
```
