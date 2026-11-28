# Offhand Companion for Linux

Spans World of Warcraft across your displays for the [Offhand](https://www.offhandwow.com/) addon, the Linux
counterpart of the Windows Offhand Companion.

**Offhand and the Offhand Companion are designed and made by N4UX** ([www.offhandwow.com](https://www.offhandwow.com/)).
Linux version by Abysmal Kabal.

This repository holds the install packages only. Download the newest one from
[Releases](https://github.com/Abysmal-Kabal/offhand-linux-companion-releases/releases/latest), or use the commands
below (no GitHub account needed). Run them one at a time.

The package manager installs everything the Companion needs by itself (Python 3, GTK 4, python-xlib, xrandr,
xwininfo, xprop and xdotool), and every package includes the frame helper. The Companion doesn't install WoW, Wine
or Lutris; it works with the game setup you already have.

## Testing: report what you find

The Linux Companion is in testing: these are test builds, and things may change or break between them. If
something doesn't work, looks wrong or could be better, please tell us:

- **Offhand Discord:** https://discord.gg/J2P3SM6pAY
- **GitHub Issues:** [report an issue here](https://github.com/Abysmal-Kabal/offhand-linux-companion-releases/issues)
- **Website:** [www.offhandwow.com](https://www.offhandwow.com/) (setup guides and help)

A report helps most with your distribution and desktop (GNOME, KDE Plasma, ...), your displays and layout, the
Companion's version (`offhand-companion --version`), what you did, what happened and what you expected, and the
output of `offhand-companion status`.

## Ubuntu 22.04+, Debian 12+, Linux Mint, Pop!_OS, Zorin, elementary

```sh
cd ~/Downloads
```
```sh
curl -LO https://github.com/Abysmal-Kabal/offhand-linux-companion-releases/releases/latest/download/offhand-companion_all.deb
```
```sh
sudo apt install ./offhand-companion_all.deb
```
```sh
rm offhand-companion_all.deb
```

## Fedora 38+, Nobara, Ultramarine

```sh
cd ~/Downloads
```
```sh
curl -LO https://github.com/Abysmal-Kabal/offhand-linux-companion-releases/releases/latest/download/offhand-companion-fedora.noarch.rpm
```
```sh
sudo dnf install ./offhand-companion-fedora.noarch.rpm
```
```sh
rm offhand-companion-fedora.noarch.rpm
```

## openSUSE Tumbleweed, GeckoLinux

```sh
cd ~/Downloads
```
```sh
curl -LO https://github.com/Abysmal-Kabal/offhand-linux-companion-releases/releases/latest/download/offhand-companion-opensuse.noarch.rpm
```
```sh
sudo zypper install --allow-unsigned-rpm ./offhand-companion-opensuse.noarch.rpm
```
```sh
rm offhand-companion-opensuse.noarch.rpm
```

`--allow-unsigned-rpm`: the package isn't signed by a repository, and zypper won't install it without this.

## Arch, Manjaro, EndeavourOS, CachyOS, Garuda

```sh
cd ~/Downloads
```
```sh
curl -LO https://github.com/Abysmal-Kabal/offhand-linux-companion-releases/releases/latest/download/offhand-companion-any.pkg.tar.zst
```
```sh
sudo pacman -U ./offhand-companion-any.pkg.tar.zst
```
```sh
rm offhand-companion-any.pkg.tar.zst
```

## Bazzite, Fedora Silverblue and Kinoite (per-user install: no sudo, no reboot)

```sh
cd ~/Downloads
```
```sh
curl -LO https://github.com/Abysmal-Kabal/offhand-linux-companion-releases/releases/latest/download/offhand-companion-per-user.tar.gz
```
```sh
tar -xzf offhand-companion-per-user.tar.gz
```
```sh
sh offhand-companion-*/install.sh
```
```sh
rm -r offhand-companion-per-user.tar.gz offhand-companion-*/
```

This copies the Companion into `~/.local`, so the download can go afterwards. Bazzite already has everything the
Companion needs. To remove it later, download and unpack it again and run `sh install.sh uninstall` from its folder.

## Why sudo

Everywhere except the per-user install, the package goes in system-wide (under `/usr`) and the package manager
fetches the dependencies from the distribution's own repositories; both need administrator rights.

## After installing

Open **Offhand Companion** from your app menu. From here on, you won't need the terminal again.

### Updates: one click

The Companion keeps itself, and the Offhand addon, up to date:

- It checks when you open it, and every few hours while it's open. When a newer Companion or Offhand addon is out,
  the **Check for Updates** button turns green and says **Update Available**.
- **Click it.** The Companion downloads the update, checks it against the release's checksums, installs it, and
  restarts on the new version.
  - **Companion updates** ask for your password, because the Companion is installed system-wide (the Bazzite
    per-user install doesn't ask).
  - **Offhand addon updates** go into the WoW folder the Companion uses: close WoW first. The previous addon folder
    is kept as a backup, and your layout keeps working without spanning again.
- You can click the button any time to check right away.

Versions before 0.8.1 can't update themselves: install once more with the line for your distribution above, and
the button takes over from there.

On GNOME, a layout that splits one display also needs the **Hide Top Bar** extension (install it with Extension
Manager).

**Checking a download** (optional): each release has `SHA256SUMS.txt`; in the folder holding the download,
`curl -LO https://github.com/Abysmal-Kabal/offhand-linux-companion-releases/releases/latest/download/SHA256SUMS.txt` and `sha256sum --check --ignore-missing SHA256SUMS.txt` should say `OK`.

## License

See [NOTICE](NOTICE): Offhand, the Offhand Companion, its logo and its design are (c) N4UX (Offhand Project), all
rights reserved.
