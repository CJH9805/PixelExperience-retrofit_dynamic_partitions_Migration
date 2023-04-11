# PixelExperience-retrofit-dynamic-partitions-Migration
## PixelExperience 动态分区迁移（一加6T）

---

First time install
1. Be on the latest OOS 11!

2. Download vbmeta.img, boot.img, super_empty.img by releases  
3. Reboot to bootloader

4. Run the following to flash the new retrofit dynamic partitions boot image + recovery: 
    - ``` fastboot flash vbmeta_a vbmeta.img ```
    - ``` fastboot flash vbmeta_b vbmeta.img ```
    - ``` fastboot flash boot_a boot.img ``` 
    - ``` fastboot flash boot_b boot.img ```
    
5. Erase the old android partitions with the following: 
    - ``` fastboot erase system_a ```
    - ``` fastboot erase system_b ```
    - ``` fastboot erase odm_a ```
    - ``` fastboot erase odm_b ```
    - ``` fastboot erase vendor_a ```
    - ```fastboot erase vendor_b ```
    
6. Boot to recovery

7. In recovery, choose Advanced -> Enter fastboot to enter fastbootd

8. Initialize the retrofit super partitions for each slot: 
    - ``` fastboot wipe-super super_empty.img ```
    - ``` fastboot set_active other ```
    - ``` fastboot wipe-super super_empty.img ```
    - ``` fastboot set_active other ```

9.Then enter our own modified TWRP or OrangeFox to install the ROM(don't flash recovery)
