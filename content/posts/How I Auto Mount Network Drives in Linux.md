---
title: How I Auto Mount Network Drives in Linux
Date: 2025-01-19
tags:
  - linux
  - network
  - cifs
  - blog
---
# Steps
1. **Install cifs-utils**: This package is necessary for mounting CIFS/SMB shares. You can install it using your distribution’s package manager. For example, on Debian-based systems, you can use:
    
    ```
    sudo apt-get install cifs-utils
    ```
    
    On Arch Linux, you can use:
    
    ```
    sudo pacman -S cifs-utils
    ```
    
2. **Create a Mount Point**: Create a directory where the network drive will be mounted. For example:
    
    ```
    sudo mkdir /mnt/networkdrivename
    ```
    
3. **Edit /etc/fstab**: Add an entry to your `/etc/fstab` file to automatically mount the network drive at boot. Use the following format:
    
    ```
    //server_ip/share_name /mnt/networkdrive cifs credentials=/etc/cifs-credentials 0 0
    ```
    
    Replace `server_ip`, `share_name`, `your_username`, and `your_password` with the appropriate values for your network drive.
    
5. **Test the Mount**: After editing `/etc/fstab`, you can test the mount without rebooting by running:
    
    ```
    sudo mount -a
    ```
    
6. **Check Logs**: If the mount fails, check the system logs for errors. For example, on Debian-based systems, you can use:
    
    ```
    sudo journalctl -xe
    ```

7. Give Plex permission to folders
```
sudo chown -R plex:plex /mnt/movies
sudo chmod -R 775 /mnt/movies
```
