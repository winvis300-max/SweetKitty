# 🐱 SweetKitty – Openbox Setup

<p align="center">
<img src="logo.png" alt="SweetKitty Logo" width="300"/>
</p>

<p align="center">
A minimal, clean and aesthetic Openbox desktop setup.
</p>

---

## ✨ Features

* Lightweight Openbox environment
* XFCE4 Panel integration
* Plank dock (macOS-like style)
* Sweet Mars GTK theme
* BeautySolar icon pack
* Clean and customizable layout

---

## 📦 Requirements

Install required packages depending on your distribution:

---

### 🟢 Debian / Ubuntu / Linux Mint

```bash
sudo apt install plank xfce4-panel nitrogen xcompmgr openbox xfce4-whiskermenu-plugin lxappearance lxsession-logout
```

---

### 🔵 Fedora / RHEL / Nobara

```bash
sudo dnf install plank xfce4-panel nitrogen xcompmgr openbox xfce4-whiskermenu-plugin lxappearance lxsession-logout
```

---

### ⚫ Arch / EndeavourOS / Manjaro / CachyOS

> ⚠️ Note: On some Arch-based systems, nitrogen may only be available in the AUR.

```bash
# If you use EndeavourOS, yay is usually preinstalled

# If yay is NOT installed:
sudo pacman -S --needed base-devel git
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si

# Install packages
yay -S plank xfce4-panel nitrogen xcompmgr openbox xfce4-whiskermenu-plugin lxappearance lxsession-logout
```

---

### 🟣 Gentoo/Calculate/Argent

```bash
sudo emerge --ask x11-wm/openbox xfce-base/xfce4-panel x11-misc/nitrogen x11-misc/xcompmgr x11-misc/plank x11-themes/lxappearance xfce-extra/xfce4-whiskermenu-plugin
```

> 💡 Note: Package names may vary slightly depending on overlays.

---

## 🚀 Installation

### 1. Clone the repository

```bash
git clone https://github.com/winvis300-max/SweetKitty.git
cd SweetKitty
```

---

### 2. Install themes and icons

```bash
tar xf Sweet-mars.tar.xz
tar xf BeautySolar.tar-*.gz
unzip elementary-Dark.zip

sudo cp -r BeautySolar/ /usr/share/icons/
sudo cp -r Sweet-mars/ /usr/share/themes/
sudo cp -r elementary-Dark/ /usr/share/plank/themes/
sudo cp wp*.jpg /usr/share/backgrounds/
```

---

### 3. Apply GTK theme

```bash
lxappearance
```

Set:

* Theme → **Sweet-mars**
* Icons → **BeautySolar**

---

### 4. Configure Plank

* Hold **Ctrl + Right Click** on dock
* Open **Preferences**
* Theme → `elementary-Dark`
* Enable **Icon Zoom**

---

### 5. Setup autostart

```bash
mkdir -p ~/.config/openbox
nano ~/.config/openbox/autostart.sh
```

Add:

```bash
plank &
xfce4-panel &
nitrogen --restore &
xcompmgr &
```

Make it executable:

```bash
chmod +x ~/.config/openbox/autostart.sh
```

---

### 6. Set wallpaper

```bash
nitrogen
```

* Add: `/usr/share/backgrounds/`
* Mode → Zoomed Fill
* Apply

---

### 7. Configure panel

* Right click panel → Panel Preferences
* Remove extra panels
* Add:

  * Whisker Menu
  * Separator
  * Clock

Settings:

* Clock → Digital (LCD)
* Whisker Menu:

  * Icon → `applications-all`
  * Enable → Settings Manager
  * Logout command → `lxsession-logout`

---

### 8. Set Openbox theme

```bash
obconf
```

Select:

* Theme → **Nightmare**

---

## 🖥️ Defaults

* File Manager → Nemo
* Terminal → Terminator
* Browser → Chromium

---

## 🎉 Done!

Log out, select **Openbox session**, and enjoy your new desktop 🎉
