# Arch-Setup

![](https://github.com/nathants/arch-setup/raw/master/arch.gif)

## Why

Bootstrapping a new computer should be easy.

## What

Install Arch Linux onto an entire disk.

The chosen disk will be COMPLETELY ERASED!

Choose your disk carefully.

This DOES NOT support partitioned install on a single disk with Windows.

This works fine to dual boot with Windows as long as there are two disks.

You will use your BIOS boot disk chooser to choose boot disk at startup.

## How

- On Linux, make Arch [ISO](https://archlinux.org/download/) USB
  - Update `if=` and `of=` with real values
  - `sudo dd bs=4M if=./archlinux-YYYY.MM.DD-x86_64.iso of=/dev/sdX status=progress oflag=sync`

- You can also use [Etcher](https://github.com/balena-io/etcher/releases) or [Rufus](https://github.com/pbatard/rufus/releases) to make the Arch USB from Windows

- Boot into USB:
  - If NVIDIA discrete GPU, at GRUB hit "e", append "nomodeset" to kernel cmdline params, hit "C-x"
  - `pacman -Sy archlinux-keyring`
  - `bash` [arch-install-ext4](./arch-install-ext4)
  - Follow the prompts carefully, if you make a mistake, reboot and try again

- Boot into Arch
  - `bash` [arch-dev-setup](./arch-dev-setup)

- Type `startx`

- The background image is the docs from [better.game](https://better.game) reboot-to-play
  - Note: `shift+f6` does not work, that is reboot-to-play only. To quit everything use `win+shift+q`
