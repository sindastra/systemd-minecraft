# [Unofficial] systemd service file for Minecraft server

### RCON

This service file requires you to install mcrcon which you can obtain here: https://github.com/Tiiffi/mcrcon

You will have to set an rcon password in your Minecraft ```server.properties```, enable RCON and then adjust the service file accordingly.

### Installation

Simply copy it to ```/etc/systemd/system/``` so that you'll have ```/etc/systemd/system/minecraft-vanilla.service```

Then run ```systemctl enable minecraft-vanilla```

Of course you should customize the service file first, to point to the actual location of your Minecraft server.

To start use ```systemctl start minecraft-vanilla```

### Removal

Simply run
```
systemctl stop minecraft-vanilla
systemctl disable minecraft-vanilla
rm /etc/systemd/system/minecraft-vanilla.service
systemctl reload-daemon
```

### Important notes

This service file is meant to be used with Minecraft vanilla, although Spigot should work.
