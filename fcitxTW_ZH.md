# Install fcitx for Taiwanese-style Mandarin typing input in Ubuntu

## Manjaro/Arch

Set the locale

```bash
sudo cp /etc/locale.gen /etc/locale.gen.orig
sudo echo "en_US.UTF-8 UTF-8" > /etc/locale.gen
sudo localectl set-locale LANG=en_US.UTF-8
sudo locale-gen
```

Install fcitx 5

```bash
sudo pacman -S --noconfirm ibus-chewing

#sudo pacman -S --noconfirm libchewing fcitx5-im  fcitx5 fcitx5-chewing fcitx5-config-qt fcitx5-gtk fcitx5-qt fcitx5-material-color

# From Manjaro https://archived.forum.manjaro.org/t/how-to-input-chinese/128392
sudo pacman -S --noconfirm fcitx fcitx-im fcitx-gtk2 fcitx-gtk3 fcitx-qt5 fcitx-configtool

sudo pacman -S --noconfirm adobe-source-han-sans-tw-fonts adobe-source-han-serif-tw-fonts
yum -S --noconfirm ttf-ms-win10-zh_tw ttf-ms-win8-zh_tw
```

1. You must FIRST add Chinese Taiwan/Traditional in:

- Settings > Region & Language > Manage Installed Languages / Language Support

2. Open Fcitx Configuration

- Uncheck "Only Show Current Language"
- Add Taiwan: Chewing

## Ubuntu

This installs fcitx on GNOME

1. You must FIRST add Chinese Taiwan/Traditional in:

- Settings > Region & Language > Manage Installed Languages / Language Support

2. ? Optionally, set the language for your User Account Settings

*If using Vrk, do not change your home folders to Chinese names since it is more difficult to type in the terminal*

- If you don't konw what Vrk is: never mind, but how did you get here you awesome web cralwer you!

3. Ctrl + Alt + T (Open the Terminal)

`sudo apt-get install fcitx fcitx-ui-qimpanel fcitx-chewing fcitx-table-cangjie3 fcitx-config-gtk`

*Some may already be installed, that's okay.*

`fcitx-qimpanel-configtool`

*Set to "Vertical", then "Apply", then exit*

*Below is less preferable, better is: Settings > Region & Language > Manage Installed Languages > Keyboard input method*

`im-config`

- Choose: OK, yes, fcitx, OK, OK

*Check if installed correctly*

`cat ~/.xinputrc`

*It should include: run_im fcitx*

*If not...*

`echo 'run_im fcitx' > ~/.xinputrc`

*Then, reboot*

`reboot`

*(Yes, you really have to reboot, even for each user)*

***Add the language***

*Choose Either:*

- In Apps, search and run: fcitx Configuration
- Click the fcitx icon > Configure

**Then...**
- + to add a language
- Deselect "Only Show Current Language"
- For Taiwan bopomofo select "Chewing", OK

All done! Have a cookie...

###
