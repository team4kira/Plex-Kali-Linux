# Plex-Kali-Linux
Plex Server on Kali-Linux

How to mount a ntfs drive on Kali Linux: 
sudo mount -t ntfs /dev/sdb1 /mnt/ntfs1
- dev represents Sata, SCSI and USB devices
- sdb1 - SD indicates a SCSI or SATA drive. B identifies a physical device, usually going chronologically e.g. sda, sdb etc, in this example we can see two SATA drives. The 1 refers to the first partition on the drive. Example: sda1 means we are looking at the first SATA drive (due to the A) and we are looking at the first partition (due to the 1)
- the command lsblk will show you what drives you have on your system
- Additional Information, after the drive is mounted the following command can be used to ascertain how much space is left on the drive: df -h /mnt/ntfs1 


Useful Commands to know for Plex-Kali Linux: 

To install .deb files: 
sudo dpkg -i <file name>
- - The dpkg -i installs the .deb package
 
If there are missing dependencies this can help fix them: 
sudo apt-get install -f
