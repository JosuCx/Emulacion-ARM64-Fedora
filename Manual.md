## Manual de Instalacion

paso 1:
    sera la actualizacion del sistema 

Code: 
    sudo dnf install update

Paso 2:Instalacion de programas

Programas a instalar, se colocaran varios programas con el fin de realizar lo mejor posible la instalacion y otros programas con el fin de problemas al momento de funcionar bien la instalacion: 

- Qemu
- kpartx
- gdb-multiarch
- binutils
- Development Tools 
- Development Libraries
- cmake 

qemu-system-aarch64 \
  -M raspi3b \
  -cpu cortex-a53 \
  -m 1G -smp 4 \
  -kernel kernel8.img \
  -drive file=rasp.img,format=raw,if=sd  \
  -dtb bcm2710-rpi-3-b-plus.dtb \
  -append "rw earlyprintk loglevel=8 console=ttyAMA0,115200 dwc_otg.lpm_enable=0 root=/dev/mmcblk0p2 rootdelay=1" \
  -nographic \
  -netdev user,id=net0,hostfwd=tcp::5555-:22 \
  -device usb-net,netdev=net0

usuario: pi