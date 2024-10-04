# Telepítse az Ubuntu Linux-ra, az elemi operációs rendszerre és a Linux Mint-re

## Ubuntu Linux 18.04 vagy újabb, elemi operációs rendszer, Linux Mint 18 vagy újabb

Telepítse a **QOwnNotes** alkalmazást az **Ubuntu Linux** operációs rendszerre (minimum 18.04) a PPA adattár használatával.

Vegye figyelembe, hogy az ARM számára is vannak csomagok az adattárban, arra az esetre, ha a QOwnNotes alkalmazást egy **Raspberry Pi** rendszeren szeretné használni.

Nyissa meg a terminált, és írja be a következő sorokat az adattár hozzáadásához és a QOwnNotes telepítéséhez.

```bash
sudo add-apt-repository ppa:pbek/qownnotes
sudo apt-get update
sudo apt-get install qownnotes
```

[Közvetlen letöltés](https://launchpad.net/~pbek/+archive/ubuntu/qownnotes/+packages)

## QOwnNotes Qt6 Preview

If you already want to try the Qt6 packages and are on Ubuntu 22.04 or newer you can use this repository:

```bash
# Remove Qt5 PPA in case you had it installed
sudo add-apt-repository --remove ppa:pbek/qownnotes

# Add Qt6 PPA
sudo add-apt-repository ppa:pbek/qownnotes-qt6

# Install QOwnNotes
sudo apt-get update
sudo apt-get install qownnotes
```

[Direct Download](https://launchpad.net/~pbek/+archive/ubuntu/qownnotes-qt6/+packages)

If you find any issues please report them on [QOwnNotes Issues on GitHub](https://github.com/pbek/QOwnNotes/issues)!

## Older Ubuntu Linux distributions and derivatives

Best try to use the AppImage from [QOwnNotes Releases on GitHub](https://github.com/pbek/QOwnNotes/releases).

Then you can change the execute-permissions on the file:

```bash
chmod a+x QOwnNotes-*.AppImage
```

Afterward you should be able to execute the AppImage to run QOwnNotes.

## OBS Repository

You may also be able to use the QOwnNotes on Ubuntu versions that aren't anymore updated on Ubuntu Launchpad then you can use the repositories from the [Open Build Service](https://build.opensuse.org/package/show/home:pbek:QOwnNotes/desktop).

Below are example calls for the xUbuntu 20.04 repository.

Run the following shell command to trust the repository.

```bash
wget http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/xUbuntu_20.04/Release.key -O - | sudo apt-key add -
```

Run the following shell commands to add the repository and install QOwnNotes from there.

```bash
sudo su -
sh -c "echo 'deb http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/xUbuntu_20.04/ /' >> /etc/apt/sources.list.d/qownnotes.list"
apt-get update
apt-get install qownnotes
```

[Direct Download](https://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/xUbuntu_20.04)
