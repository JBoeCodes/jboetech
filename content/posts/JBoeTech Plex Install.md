---
title: JBoeTech Plex Install
Date: 2025-03-03
tags:
  - linux
  - network
  - plex
  - server
  - blog
---
Distro: Ubuntu Server
notes: Install OpenSSH
dependencies: nano, cifs-utils, Plex, OpenSSH
See also: [[How I Auto Mount Network Drives in Linux]]
1. Add Plex to the repo:
```
echo deb [https://downloads.plex.tv/repo/deb](https://downloads.plex.tv/repo/deb) public main | sudo tee /etc/apt/sources.list.d/plexmediaserver.list
```

```
curl [https://downloads.plex.tv/plex-keys/PlexSign.key](https://downloads.plex.tv/plex-keys/PlexSign.key) | sudo apt-key add -
```

2. Update the repo
```
sudo apt update
```

3. Install Plex
```
sudo apt install plexmediaserver
```

4. Auto start Plex
```
sudo systemctl enable plexmediaserver.service
```

5. Connect to the web server:
ip.address:32400/web

6. Connect your files
If you have not added network shares to your plex machine, see [[01192025 Auto Mount Network Drives in Linux]]
