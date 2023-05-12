# arch-setup

## why

bootstrapping a new laptop should be easy.

## how

- make arch [iso](https://archlinux.org/download/) usb
  - `sudo dd bs=4M if=./archlinux-YYY.MM.DD-x86_64.iso of=/dev/sdX status=progress oflag=sync`

- boot into usb:
  - if nvidia discrete gpu, at grub hit "e", append "nomodeset" to kernel cmdline params, hit "C-x"
  - `pacman -Sy archlinux-keyring`
  - `bash` [arch-install-ext4](./arch-install-ext4)

- boot into arch
  - `bash` [arch-dev-setup](./arch-dev-setup)
