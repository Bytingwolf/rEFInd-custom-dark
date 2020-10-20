## rEFInd-custom-dark, black & white edition

[rEFInd](http://www.rodsbooks.com/refind/) is a simple boot manager for UEFI-based systems. This is a clean and minimal theme for it.

![rEFInd minimal, B&W edition](http://i.imgur.com/QlnSxSq.png)

### Usage

 1. Locate your rEFInd EFI directory. This is commonly `/boot/EFI/refind`,
    though it will depend on where you mount your ESP and where rEFInd is
    installed. `fdisk -l` and `mount` may help.

 2. Clone this repository into your rEFInd configuration directory.

 3. To enable the theme add `include rEFInd-custom-dark/theme.conf` at the end of
    `refind.conf`.

Here's an example menuentry configuration:

```nginx
menuentry "Arch Linux" {
	icon /EFI/refind/rEFInd-custom-dark/icons/os_arch.png
	loader vmlinuz-linux
	initrd initramfs-linux.img
	options "rw root=UUID=dfb2919d-ff78-48db-a8a7-23f7542c343a loglevel=3"
}

menuentry "Windows" {
	icon /EFI/refind/rEFInd-custom-dark/icons/os_win.png
	loader /EFI/Microsoft/Boot/bootmgfw.efi
}

menuentry "OSX" {
	icon /EFI/refind/rEFInd-custom-dark/icons/os_mac.png
	loader /EFI/Apple/Boot/bootmgfw.efi
}
```

Entries that are autodetected should also show the proper icons.
Some entries have been modified to clean up miscellaneous boot options (such as "Boot Windows with Shell", grubx64.efi) which can simply be enabled back by changing it in theme.conf.

### Attribution

This theme is based on the [rEFInd-minimal][rEFInd-minimal] theme by [EvanPurkhiser][EvanPurkhiser].

Most of the OS icons are from [Lightness for burg][icons] by [SWOriginal][icon-author]; they were modified to match the black background of this theme.

The Windows icon is from the [rEFInd Next][rEFInd-Next] theme by [sdbinwiiexe][sdbinwiiexe]; it was scaled and aligned to the selection icons in this theme.

[EvanPurkhiser]: https://github.com/EvanPurkhiser
[rEFInd-minimal]: https://github.com/EvanPurkhiser/rEFInd-minimal
[icons]: http://sworiginal.deviantart.com/art/Lightness-for-burg-181461810
[icon-author]: http://sworiginal.deviantart.com
[rEFInd-Next]: http://sdbinwiiexe.deviantart.com/art/rEFInd-Next-Theme-407754566
[sdbinwiiexe]: http://sdbinwiiexe.deviantart.com
