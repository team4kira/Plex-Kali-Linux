# Plex-Kali-Linux
Plex Server on Kali-Linux

How to mount a ntfs drive on Kali Linux: 
`sudo mount -t ntfs /dev/sdb1 /mnt/ntfs1`
- dev represents Sata, SCSI and USB devices
- sdb1 - SD indicates a SCSI or SATA drive. B identifies a physical device, usually going chronologically e.g. sda, sdb etc, in this example we can see two SATA drives. The 1 refers to the first partition on the drive. Example: sda1 means we are looking at the first SATA drive (due to the A) and we are looking at the first partition (due to the 1)
- the command lsblk will show you what drives you have on your system
- Additional Information, after the drive is mounted the following command can be used to ascertain how much space is left on the drive: df -h /mnt/ntfs1 


Useful Commands to know for Plex-Kali Linux: 

To install .deb files: sudo dpkg -i file_name.deb 
- The dpkg -i installs the .deb package
 
If there are missing dependencies this can help fix them: 
sudo apt-get install -f

Installing Plex Media Server 

- Open Terminal
- Enter: `sudo apt update`
- Enter: `sudo dpkg -i plexmediaserver_ file.deb`
  - Get the file from https://www.plex.tv/en-ca/media-server-downloads/
-  Check if plex media server is running: `sudo systemctl status plexmediaserver`
   - If it is not running enter: `sudo systectl start plexmediaserver`
- If you're using UFW Firewall Ensure to Grant Access to the Following:
  - `sudo ufw allow 32400`
  - `sudo ufw app update plexmediaserver`
  - `sudo ufw allow plexmediaserver-all`
- Check the status of firewall rules: `sudo ufw status` 

Configure Plex Media Server
- Ensure you have a folder for the media you want access example: /home/Kali/HomeVideos
  - To make a directory enter: `sudo mkdir -p /Directory/Location`
  - You can use a directory from a external harddrive just remember to mount the drive. See above for instruction on how to mount different drives in Linux
- The folder would need to be readable and writeable
  - To ensure the enter the following: `sudo chown -R plex: /home/Kali/HomeVideos`
