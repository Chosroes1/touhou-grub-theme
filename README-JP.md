東方虚御履 ~Cyberadise Bootloader
====
<img width="2880" height="1800" alt="例图" src="https://github.com/user-attachments/assets/41380705-44e1-4592-baf2-9070153ba81a" />


導入方法
----
1.[Releases](https://github.com/Chosroes1/touhou-grub-theme/releases/tag/v1.0) から、ご使用のモニター解像度に対応する圧縮ファイルを選択します。<br>
2.解凍後、`th-cb/` フォルダを `/boot/grub/themes/` に移動します（Fedoraなどのシステムをご利用の場合は `/boot/grub2/themes/` に移動してください）。以下の例では、解像度 2880x1800、デフォルトのダウンロード先を `~/Downloads`、解凍ツールを gzip と想定しています。実際の環境に合わせてコマンドを修正してください。
``` bash
  tar -xzvf ~/Downloads/2880x1800.tar.gz -C ~/Downloads/
  sudo mv ~/Downloads/2880x1800/th-cb /boot/grub/themes/
```
3.設定ファイル `/etc/default/grub` を編集します。<br>
```bash
sudo vim /etc/default/grub
```
  `GRUB_TERMINAL_OUTPUT=console` を探し、`console` を `gfxterm` に変更します。<br>
  `GRUB_THEME=` を探すか追加してコメントアウトを外し、テーマのパスを追記します。`GRUB_THEME="/boot/grub/themes/th-cb/theme.txt"` と設定してください。<br>
  保存して終了します。<br>
4.GRUB を更新します。
``` bash
 sudo grub-mkconfig -o /boot/grub/grub.cfg
```
  Fedora ユーザーはこちらを使用してください：
```
  sudo grub2-mkconfig -o /boot/grub2/grub.cfg
  #または
  #sudo grub2-mkconfig -o /boot/efi/EFI/fedora/grub.cfg
```
5.再起動します。
```bash
reboot
```

使用素材
----
Character Illustration: MMJ #pixiv 【フリー素材】新博麗霊夢立ち絵2023 https://www.pixiv.net/artworks/112223416 <br>
Original Background： Freepik www.freepik.com <br>
Title Font: 装甲明朝 https://flopdesign.booth.pm/items/1028555 <br>
Suntile Font: ROG Fonts <br>
Menu Font: 猫啃故障宋 https://fonts.zeoseven.com/items/831/ <br>
Terminal Font: DejaVu Sans Mono <br>
Other Font: 文泉驿正黑 <br>
Icons/Terminal Box: From https://github.com/Coopydood/HyperFluent-GRUB-Theme <br>

注意事項
----
本テーマは 2880x1800 解像度のモニターでのみ動作確認を行っており、他の解像度でのテストは実施していません。他の解像度で問題が発生した場合は、Issue でご報告いただければ、可能な限り早急に修正いたします。<br>
日本語環境で GRUB を更新する場合、文泉驿（WenQuanYi）のフォントファイル（wqy.pf2）を削除しないでください。削除すると、巨大な「猫啃故障宋」フォントがターミナルを埋め尽くしてしまいます。また、「文泉驿正黑」をターミナルフォントとして設定しないでください。設定するとターミナル枠の表示位置に異常が生じます。
