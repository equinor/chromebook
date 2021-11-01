# Installing apps

- PWA
- Flatpak
- Deb-files
- Play Store
  - Mostly Android apps and some PWAs (Zoom for Chrome for example)
  - Most Android apps are for phones (Opera is an exception)

A PWA will have an install icon in the right hand side of the address bar. Web apps that are _not_ PWAs can still be “installed” by clicking … → “more tools” → “create shortcut” and then ticking off “Open as window”.

## Crostini

### Installing MS Visual Code

```
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg

sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/

sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'

rm -f packages.microsoft.gpg

sudo apt install apt-transport-https
sudo apt update
sudo apt install code # or code-insiders
```
