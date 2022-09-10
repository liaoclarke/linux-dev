Run Linux in emulation with:

  qemu-system-riscv64 -smp 4 -m 4G -M virt -bios ./fw_jump.elf -kernel ./Image -append "rootwait root=/dev/vda ro console=ttyS0" -drive file=./rootfs.ext2,format=raw,id=hd0 -device virtio-blk-device,drive=hd0 -netdev ${QEMU_NETDEV},id=net0 -device virtio-net-device,netdev=net0 -nographic # qemu_riscv64_virt_defconfig

The login prompt will appear in the terminal that started Qemu.
