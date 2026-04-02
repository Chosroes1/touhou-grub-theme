東方虚御履 ~Cyberadise Bootloader
====

<img width="2880" height="1800" alt="例图" src="https://github.com/user-attachments/assets/41380705-44e1-4592-baf2-9070153ba81a" />



Configuration
----
1. Go to [Releases](https://github.com/Chosroes1/touhou-grub-theme/releases/tag/v1.0) and select the archive corresponding to your screen resolution.<br>
2. Extract the archive and move the `th-cb/` folder to `/boot/grub/themes/` (Fedora and similar system users should move it to `/boot/grub2/themes/`). The example below uses the 2880x1800 resolution, assumes the default download path is `~/Downloads`, and uses `gzip` as the extraction tool. Please adjust the commands according to your actual situation.
``` bash
  tar -xzvf ~/Downloads/2880x1800.tar.gz -C ~/Downloads/
  sudo mv ~/Downloads/2880x1800/th-cb /boot/grub/themes/
```
3.Edit the `/etc/default/grub` configuration file.
```bash
sudo vim /etc/default/grub
```
  Find `GRUB_TERMINAL_OUTPUT=console` and change `console` to `gfxterm`.<br>
  Find or add `GRUB_THEME=`, uncomment it, and append the theme path. Set it to `GRUB_THEME="/boot/grub/themes/th-cb/theme.txt"`.<br>
  Save and exit.<br>
4. Update GRUB.
``` bash
 sudo grub-mkconfig -o /boot/grub/grub.cfg
```
  For Fedora users, please use:
```
  sudo grub2-mkconfig -o /boot/grub2/grub.cfg
  #Or
  #sudo grub2-mkconfig -o /boot/efi/EFI/fedora/grub.cfg
```
5.重启
```bash
reboot
```

Assets Used
----
Character Illustration: MMJ #pixiv 【フリー素材】新博麗霊夢立ち絵2023 https://www.pixiv.net/artworks/112223416 <br>
Original Background： Freepik www.freepik.com <br>
Title Font: 装甲明朝 https://flopdesign.booth.pm/items/1028555 <br>
Suntitile Font: ROG Fonts <br>
Menu Font: 猫啃故障宋 https://fonts.zeoseven.com/items/831/ <br>
Terminal Font: DejaVu Sans Mono <br>
Other Font: 文泉驿正黑 <br>
Icons/Terminal Box: From https://github.com/Coopydood/HyperFluent-GRUB-Theme <br>

Notes
----
This theme has only been tested on a 2880x1800 resolution monitor; other resolutions have not been tested. If you encounter any issues with other resolutions, please open an issue and I will fix it as soon as possible.
