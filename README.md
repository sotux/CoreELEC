# CoreELEC for Phicomm N1

This branch builds CoreELEC 21.3 (`Amlogic-ng`, kernel `amlogic-4.9`) for the Phicomm N1
(Amlogic S905D). The device uses its vendor u-boot, which can only boot a plain
`Image` together with a standalone `uInitrd`, hence the N1 specific `Phicomm_N1`
subdevice in `projects/Amlogic-ce/devices/Amlogic-ng`.

Install by writing the `CoreELEC-Amlogic-ng.arm-*.img.gz` to a USB drive. Upgrades are
done by placing the update package (`CoreELEC-Amlogic-ng.arm-*.tar`) in
`/storage/.update/` and rebooting; `update.sh` refreshes `boot.ini`, `dtb.img`,
`s905_autoscript` and `uInitrd` automatically.

Build with:

    make PROJECT=Amlogic-ce DEVICE=Amlogic-ng ARCH=arm image

`ARCH` is forced to `arm` for `Amlogic-ng`, and `PROJECT` defaults to `Amlogic-ce`,
so `make DEVICE=Amlogic-ng image` is enough. The kernel is fetched from the
`phicomm-n1` branch of https://github.com/sotux/linux-amlogic (pinned by
`PKG_VERSION` in `projects/Amlogic-ce/packages/linux/package.mk`), so that branch
has to be pushed before building.

# CoreELEC

CoreELEC is a 'Just enough OS' Linux distribution for running the award-winning [Kodi](https://kodi.tv) software on popular low-cost hardware. CoreELEC is a minor fork of [LibreELEC](https://libreelec.tv), it's built by the community for the community. [CoreELEC website](http://coreelec.org).

**Issues & Support**

Please report issues via the CoreELEC [Forum](https://discourse.coreelec.org).

**Donations**

At this moment we do not accept Donations. We are doing this for fun not for profit.

**License**

CoreELEC original code is released under [GPLv2](https://www.gnu.org/licenses/gpl-2.0.html).

**Copyright**

As CoreELEC includes code from many upstream projects it includes many copyright owners. CoreELEC makes NO claim of copyright on any upstream code. Patches to upstream code have the same license as the upstream project, unless specified otherwise. For a complete copyright list please checkout the source code to examine license headers. Unless expressly stated otherwise all code submitted to the CoreELEC project (in any form) is licensed under [GPLv2](https://www.gnu.org/licenses/gpl-2.0.html). You are absolutely free to retain copyright. To retain copyright simply add a copyright header to each submitted code page. If you submit code that is not your own work it is your responsibility to place a header stating the copyright.
