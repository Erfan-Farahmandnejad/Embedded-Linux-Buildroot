# Building a Lightweight Custom OS with Buildroot🐧🐧

This repository documents the process of building a minimal, custom Linux distribution from scratch for the `x86_64` architecture. The project leverages the **Buildroot** automation tool to configure, compile, and generate a bootable OS image, demonstrating key concepts in embedded systems and operating system design. This was completed as a final project for the Operating Systems course at the University of Isfahan.


## Project Overview

The primary objective of this project was to gain hands-on experience with the low-level components of a Linux system. This involved a deep dive into the roles of the bootloader (GRUB2), the Linux kernel, and the root filesystem (BusyBox and glibc). The final output is a lightweight, bootable Linux system that can be run from a USB drive on modern UEFI-based computers, complete with essential utilities and SSH capabilities for remote management.


## Technical Details

* **Automation Tool:** Buildroot `2025.02`
* **Target Architecture:** `x86_64`
* **Linux Kernel Version:** `6.1.24` (LTS)
* **C Library:** `glibc`
* **Bootloader:** `GRUB2` for `x86_64-efi` systems
* **Init System:** `BusyBox`
* **Core Packages:**
    * `dropbear` for a lightweight SSH server and client.
    * Core utilities provided by BusyBox.


## Key Features

* **Minimal Footprint:** The entire OS is configured to be small and efficient, including only necessary components.
* **Custom Configuration:** The system hostname, welcome banner, and root password have been customized.
* **UEFI Bootable:** The generated image is designed to boot on modern PCs using the UEFI standard.
* **Remote Access:** Integrated `dropbear` SSH server allows for remote command-line access.


## Build Process

The complete, step-by-step instructions for reproducing this build are available in the detailed PDF report. The general workflow is as follows:

1.  **Setup Environment:** Install prerequisite packages on a host Linux system (e.g., Ubuntu).
2.  **Configure Buildroot:** Use `make menuconfig` to select the target architecture, kernel version, bootloader, and desired software packages. The configuration for this project is saved in the `.config` file.
3.  **Compile the System:** Run `make` to have Buildroot download, configure, and compile the entire toolchain, kernel, and all selected packages.
4.  **Prepare Bootable Media:** Partition and format a USB drive, then copy the generated kernel (`bzImage`), root filesystem (`rootfs.ext4`), and EFI bootloader files to the appropriate partitions.


## Full Documentation

For a comprehensive guide, including the exact configuration settings, commands used, challenges encountered, and screenshots of the final running system, please refer to the full **Project Report PDF** included in this repository.

---
*Developed by Erfan Farahmandnejad.*
