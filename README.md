# onhub-openwrt
Instructions for install openwrt onto an OnHub

## rough plan
### factory reset (so we're in a clean state)
* download Recovery image (from https://dl.google.com/dl/edgedl/chromeos/recovery/chromeos_9334.41.3_whirlwind_recovery_stable-channel_mp.bin.zip)
* store this zip somewhere permanent in case google removes the download links
* flash to usb drive (ask bnorris for command, for when google removes support for the tool?).  Maybe use Etcher https://www.balena.io/etcher/?
* enable developer mode https://www.exploitee.rs/index.php/Rooting_The_Google_OnHub#:~:text=Enabling%20%22Developer%20Mode%22%20on%20the%20OnHub,-Make%20sure%20your&text=Hold%20down%20the%20reset%20switch,careful%20as%20it's%20extremely%20delicate.)&text=After%20the%20LED%20starts%20blinking,should%20now%20start%20blinking%20purple.
### creating openwrt image
* create virtualbox builder? https://openwrt.org/docs/guide-developer/buildserver_virtualbox.  Or maybe use docker https://github.com/openwrt/docker
* set permissions https://github.com/openwrt/openwrt/issues/9545
* start working on a fork https://openwrt.org/docs/guide-developer/working-with-github-pr
* add a DTS file and other relevant files like was done for google wifi: https://git.openwrt.org/?p=openwrt/openwrt.git;a=commit;h=f1c041e34f9742fcdd0c8c65f69888d3ec580541
* chrominum dts file might be https://chromium.googlesource.com/chromiumos/third_party/kernel/+/chromeos-3.14/arch/arm/boot/dts/qcom-ipq8064-whirlwind-sp5.dts (or maybe the sp3)
* flash with Balena Etcher? https://www.balena.io/etcher/

###

### future to make it even nicer
* instead of `dd` commands use in Google Wifi OpenWRT page, can we look at the source of `/usr/sbin/chromeos-install` and see what it does? https://chromium.googlesource.com/chromiumos/docs/+/HEAD/developer_guide.md#Installing-your-ChromiumOS-image-to-your-hard-disk

## Reference docs
* openwrt thread about support https://forum.openwrt.org/t/onhub-tp-link-tgr1900-future-support/17899/25?page=2
* List of ChromeOS board names / targets https://www.chromium.org/chromium-os/developer-information-for-chrome-os-devices/
* onhub page in chromium https://www.chromium.org/chromium-os/developer-information-for-chrome-os-devices/tp-link-onhub-tgr1900/
* how to build an image of chromeos for a specific board, using debug mode, and disabling rootfs verification https://chromium.googlesource.com/chromiumos/docs/+/HEAD/developer_guide.md#build-the-packages-for-your-board
* how device trees work in Linux https://elinux.org/Device_Tree_Usage
* google wifi (similarish) OpenWRT page https://openwrt.org/toh/google/wifi
* explotiee.rs site about rooting the onhub https://www.exploitee.rs/index.php/Rooting_The_Google_OnHub#:~:text=Enabling%20%22Developer%20Mode%22%20on%20the%20OnHub,-Make%20sure%20your&text=Hold%20down%20the%20reset%20switch,careful%20as%20it's%20extremely%20delicate.)&text=After%20the%20LED%20starts%20blinking,should%20now%20start%20blinking%20purple.
* openwrt developer guide https://openwrt.org/docs/guide-developer/start
* openwrt commit that added support for Google Wifi https://git.openwrt.org/?p=openwrt/openwrt.git;a=commit;h=f1c041e34f9742fcdd0c8c65f69888d3ec580541
* chromium dts files for Onhub: https://chromium.googlesource.com/chromiumos/third_party/kernel/+/chromeos-3.14/arch/arm/boot/dts/qcom-ipq8064-whirlwind-sp5.dts
* openwrt guide about dts files https://openwrt.org/docs/guide-developer/device-support-policies
* openwrt guide about adding a new device https://openwrt.org/docs/guide-developer/add.new.device
