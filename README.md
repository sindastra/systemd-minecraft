# [Unofficial] systemd service file for Minecraft server

Have you been using ```screen``` like a n00b? Or worse, a service file that just starts screen?

Stop that nonsense and use a proper systemd service file instead!

### RCON

This service file requires you to install mcrcon which you can obtain here: https://github.com/Tiiffi/mcrcon

You will have to set an rcon password (and enable RCON) in your Minecraft ```server.properties``` and then adjust the service file accordingly.

### Installation

Set up RCON first as stated above and then:

Modify minecraft-vanilla.service so that the WorkingDirectory points to the directory with your minecraft's server.jar
Modify minecraft-vanilla.service so that ```YOUR_RCON_PASSWORD``` is your actual RCON password.
Modify minecraft-vanilla.service so that ```User``` and ```Group``` match the user and group you want to run the server as.

Then install the service file with:

```
sudo install -o root -g root -m 0644 minecraft-vanilla.service /etc/systemd/system/minecraft-vanilla.service
sudo systemctl daemon-reload
sudo systemctl enable minecraft-vanilla.service
sudo systemctl start minecraft-vanilla.service
```

### Removal

Simply run
```
sudo systemctl stop minecraft-vanilla
sudo systemctl disable minecraft-vanilla
sudo rm /etc/systemd/system/minecraft-vanilla.service
sudo systemctl reload-daemon
```

### Important notes

This service file is meant to be used with Minecraft vanilla.

If you are using Spigot, you must use ```minecraft-spigot.service``` instead.

###### "Minecraft" is a trademark of Mojang Synergies AB
###### This project is not affiliated with Minecraft
