# Resize Home Partition

## 1. Volume Group

1. Next comand show volume group

   ```bash
   vgdisplay
   ```

2. Then make new partition in Gparted (linux lvm)

3. Now extend original volume group using above partition

   ```bash
   vgextend [Volume Group Name] /dev/[New Partition Name]
   ```



## 2. Logical Volume

1. Next command show logical volume list

   ```bash
   lvdisplay
   ```

2. Now extend logical volume (ex) /dev/korora/home)

   ```bash
   lvextend --size +100G /dev/korora/home
   ```



## 3. Refresh Mapper

1. Next command refresh mapper (ex) /dev;mapper/korora-home)

   ```bash
   resize2fs /dev/mapper/korora-home
   ```

   ​