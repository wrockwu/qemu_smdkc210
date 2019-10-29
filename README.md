# For qemu-system-arm smdkc210(dtb is exynos4210_smdkv310.dtb)
qemu command:
- qemu-system-arm -M smdkc210 -m 1024M -smp 2 -kernel arch/arm/boot/zImage -dtb arch/arm/boot/dts/exynos4210-smdkv310.dtb -nographic -append "console=ttySAC0,115200n8" -initrd ../ramdisk

# Ramdisk build command
- apt-get install genext2fs
- genext2fs -b 4096 -d tiny4412_ramdisk ramdisk

#linux4.4 zImage 
- cp qemu_c210.config kernel/.config
- make
