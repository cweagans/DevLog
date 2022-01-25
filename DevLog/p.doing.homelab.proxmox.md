---
id: VwhzQnkxQgKYvCPoK2XeX
title: Proxmox
desc: ''
updated: 1642570336454
created: 1641631765756
---

![[n.hypervisor]]

## Proxmox setup steps

0. [Great installation video][0]
1. [download iso][1]
2. Burn iso to a flashdrive
   1. linux: `dd` command
   2. Windows: [rufus][2]
   3. MacOS: [Etcher][3]
3. Put flash drive into target machine
4. Boot from the flash drive
5. Follow the prompts and fill in the information
   1. Note: i did have to configure my disks in some of the boot menus to make a single logical volume RAID 5 configuration
   2. The in the Proxmox installer i just selected ext4 for the file system
   3. Will use ZFS on [[p.doing.homelab.servers.fafnir]]
6. fill in network inforation
   1. Much of it can be gleaned from your router console
   2. `ifconfig get default | grep gateway` for the default gateway
   3. for MacOS to find [[n.protocol.dns]] server just search for `DNS` in *system preferences*
7. Once proxmox is finished bootstrapping and restarts the server, remove the flash media
8. if screen loads to a console then you can just transition back to your main machine and use the web interface to finish.
9. management console is at: `https://#.#.#.#:8006` (replace `#` with valid ipv4 address)
10. connection will be unsecure and that's okay, proceed anyhow
11. login as `root` with the password you previously set.
12. Ignore subscription popup, its FOSS unless you want enterprise subscription

[0]: https://youtu.be/azORbxrItOo
[1]: https://proxmox.com/en/downloads
[2]: https://rufus.ie/en/
[3]: https://www.balena.io/etcher/

- TODO <https://youtu.be/GoZaMgEgrHw>