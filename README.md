東方虚御履 ~Cyberadise Bootloader
====

<img width="2880" height="1800" alt="例图" src="https://github.com/user-attachments/assets/41380705-44e1-4592-baf2-9070153ba81a" />


[简体中文](https://github.com/Chosroes1/touhou-grub-theme/blob/main/README.md) [English](https://github.com/Chosroes1/touhou-grub-theme/blob/main/README-EN.md)<br>

配置方法
----
1.在[Releases](https://github.com/Chosroes1/touhou-grub-theme/releases/tag/v1.0)中选择自己屏幕分辨率对应的压缩包。<br>
2.解压，将th-cb/移动到`/boot/grub/themes/`（Fedora等系统用户需移动到/boot/grub2/themes/）。下方示例以2880x1800为例，默认下载地址为`~/Downloads`，解压工具为gzip，请根据实际情况进行修正。
``` bash
  tar -xzvf ~/Downloads/2880x1800.tar.gz -C ~/Downloads/
  sudo mv ~/Downloads/2880x1800/th-cb /boot/grub/themes/
```
3.编辑`/etc/default/grub`配置文件。<br>
```bash
sudo vim /etc/default/grub
```
  找到`GRUB_TERMINAL_OUTPUT=console`,把console改为gfxterm。<br>
  找到或添加GRUB_THEME=，取消注释，并添加主题路径。设置为`GRUB_THEME="/boot/grub/themes/th-cb/theme.txt"`。<br>
  保存并退出。<br>
4.更新grub。
``` bash
 sudo grub-mkconfig -o /boot/grub/grub.cfg
```
  Fedora用户请使用
```
  sudo grub2-mkconfig -o /boot/grub2/grub.cfg
  #或
  #sudo grub2-mkconfig -o /boot/efi/EFI/fedora/grub.cfg
```
5.重启
```bash
reboot
```

使用素材
----
Character Illustration: MMJ #pixiv 【フリー素材】新博麗霊夢立ち絵2023 https://www.pixiv.net/artworks/112223416 <br>
Original Background： Freepik www.freepik.com <br>
Title Font: 装甲明朝 https://flopdesign.booth.pm/items/1028555 <br>
Suntitile Font: ROG Fonts <br>
Menu Font: 猫啃故障宋 https://fonts.zeoseven.com/items/831/ <br>
Terminal Font: DejaVu Sans Mono <br>
Other Font: 文泉驿正黑 <br>
Icons/Terminal Box: From https://github.com/Coopydood/HyperFluent-GRUB-Theme <br>

备注
----
本主题仅在2880x1800分辨率的显示器上进行过测试，其他分辨率并未经过测试。如在其他分辨率下出现问题，请提出，我会尽快修改。<br>
如在中文环境下更新GRUB，请勿删除文泉驿的字体文件（即wqy.pf2），否则会导致巨大的猫啃故障宋占据终端。也不要将文泉驿正黑设为终端字体，否则会导致终端框位置出现异常。
