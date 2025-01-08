# arch-setup

## why

bootstrapping a new computer should be easy.

## what

install arch linux onto an entire disk.

the chosen disk will be COMPLETELY ERASED!

choose your disk carefully.

this DOES NOT support partitioned install on a single disk with windows.

this works fine to dual boot with windows as long as there are two disks.

you will use your bios boot disk chooser to choose boot disk at startup.

## how

- on linux, make arch [iso](https://archlinux.org/download/) usb
  - update `if=` and `of=` with real values
  - `sudo dd bs=4M if=./archlinux-YYYY.MM.DD-x86_64.iso of=/dev/sdX status=progress oflag=sync`

- you can also use [etcher](https://github.com/balena-io/etcher/releases) or [rufus](https://github.com/pbatard/rufus/releases) to make the arch usb from windows

- boot into usb:
  - if nvidia discrete gpu, at grub hit "e", append "nomodeset" to kernel cmdline params, hit "C-x"
  - `pacman -Sy archlinux-keyring`
  - `bash` [arch-install-ext4](./arch-install-ext4)
  - follow the prompts carefully, if you make a mistake, reboot and try again

- boot into arch
  - `bash` [arch-dev-setup](./arch-dev-setup)

- type `startx`

- the background image is the docs from [better.game](https://better.game) reboot-to-play
  - note: `shift+f6` does not work, that is reboot-to-play only. to quit everything use `win+shift+q`
