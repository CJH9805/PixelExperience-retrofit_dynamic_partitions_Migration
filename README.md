# PE-retrofit_dynamic_partitions-Migration
PixelExperience-retrofit_dynamic_partitions-Migration（For OnePlus 6T）

First time install
1. Be on the latest OOS 11! tuto
2. Download vbmeta.img, boot.img, super_empty.img: https://sourceforge.net/projects/evolution-x/files/fajita/
3. Reboot to bootloader
4. Run the following to flash the new retrofit dynamic partitions boot image + recovery: 
    - fastboot flash vbmeta_a vbmeta.img 
    - fastboot flash vbmeta_b vbmeta.img fastboot 
    - flash boot_a boot.img 
    - fastboot flash boot_b boot.img
5. Erase the old android partitions with the following: 
    - fastboot erase system_a 
    - fastboot erase system_b 
    - fastboot erase odm_a 
    - fastboot erase odm_b 
    - fastboot erase vendor_a 
    - fastboot erase vendor_b
