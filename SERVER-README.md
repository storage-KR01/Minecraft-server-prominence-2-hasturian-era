# Prominence II: Hasturian Era 4.1.3

Server folder: `/home/ubuntu/minecraft-prominence-2-hasturian-era`
Minecraft 1.20.1; Fabric 0.19.3; Java 17; RAM 2–8 GB.
Client must use matching modpack version 4.1.3.
Default game port: TCP 25565. Online authentication remains enabled.

## Management

Run as ubuntu:

```sh
systemctl --user status minecraft-prominence
systemctl --user stop minecraft-prominence
systemctl --user start minecraft-prominence
systemctl --user restart minecraft-prominence
journalctl --user -u minecraft-prominence -f
```

The service starts at boot and continues after logout (user lingering enabled).
The service runs the Fabric launcher directly; service RAM settings are in
`/home/ubuntu/.config/systemd/user/minecraft-prominence.service`.
After editing the service, run `systemctl --user daemon-reload` and restart it.
`variables.txt` configures manual `bash start.sh` runs only.
Do not run the manual script while the service is running.

Configuration: `server.properties`; log: `logs/latest.log`; world: `world/`.
Stop the server before copying world files for backups.
