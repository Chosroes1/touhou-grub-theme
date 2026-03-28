東方虚御履 ~Cyberadise Bootloader
====
1.在[Release](https://github.com/Chosroes1/touhou-grub-theme/releases/tag/v1.0)中选择自己屏幕分辨率对应的压缩包。/<br>
2.解压，将th-cb/移动到`/boot/grub/themes/`（Fedora等系统用户需移动到/boot/grub2/themes/）。下方示例以2880x1800为例，默认下载地址为`~/Downloads`，解压工具为gzip，请根据实际情况进行修正。
``` bash
  tar -xzvf ~/Downloads/2880x1800.tar.gz -C ~/Downloads/
  sudo mv ~/Downloads/2880x1800/th-cb /boot/grub/themes/
```
3.编辑`/etc/default/grub`，找到`GRUB_TERMINAL_OUTPUT=console`,把console改为gfxterm。/<br>
  找到或添加GRUB_THEME=，取消注释，并添加主题路径。`GRUB_THEME="/boot/grub/themes/th-cb/theme.txt"`。/<br>
  保存并退出。
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
