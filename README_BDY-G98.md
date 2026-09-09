# EDK2 UEFI Firmware for RK3588 - BDY-G98 Platform

This repository contains EDK2 UEFI firmware for Rockchip RK3588-based platforms, with added support for the **BDY-G98** platform.

## Origin

Forked from [edk2-porting/edk2-rk3588](https://github.com/edk2-porting/edk2-rk3588).

## BDY-G98 Hardware Specifications

- **SoC**: Rockchip RK3588 (4×Cortex-A55 + 4×Cortex-A76)
- **PMIC**: RK8602 (0x42) + RK8603 (0x43) on I2C0
- **Storage**: 2× NVMe (PCIe 3.0 x2 each) + eMMC
- **Ethernet**: 2× YT9215 DSA switches (8 ports) + 2× RTL8125 PCIe
- **Display**: 1× HDMI
- **Device Tree**: rk3588-bdy-g98.dtb (vendor mode)

## Building

\\\ash
git clone --recursive https://github.com/a276519803-sudo/edk2-rk3588-bdy-g98.git
cd edk2-rk3588-bdy-g98
./build.sh --device bdy-g98 --release Release
\\\

Output: \RK3588_NOR_FLASH.img\

## ⚠️ Disclaimer / 免责声明

**This firmware is UNTESTED. Use at your own risk.**

**本固件未经测试，风险自担。**

- The platform configuration (GPIO pins, PCIe reset, LED, fan PWM) was derived from the device tree and may not match the actual hardware.
- Flashing incorrect firmware may brick your device.
- Always verify hardware configurations before flashing.
- No warranty is provided, express or implied.

## Platform Configuration Files

- \configs/bdy-g98.conf\ - Device configuration
- \edk2-rockchip/Platform/BDY/BDYG98/\ - Platform DSC, FDF, ACPI, DeviceTree, and Library files
- \devicetree/vendor/rk3588-bdy-g98.dtb\ - Vendor device tree blob

## License

BSD-2-Clause-Patent (same as upstream EDK2).
