# Update packages

_Updates your system applications_

```shell
sudo apt update
sudo apt dist-upgrade -y
```

# Fix Windows time

_Fix Windows time zone freakout when dual booting_

```shell
timedatectl set-local-rtc 1 --adjust-system-clock
```

# Configure Settings

_Change the system settings_

- Appearance -> Window colors -> Dark
- Settings -> Privacy -> Screen Lock -> Blank Screen Delay -> Never
- Settings -> Privacy -> Screen Lock -> Automatic Screen Lock -> Off
- Settings -> Privacy -> Screen Lock -> Show Notifications on Lock Screen -> Off
- Settings -> Privacy -> Diagnostics -> Problem Reporting -> Send error reports to Canonical -> Never
- Settings -> Sound -> Volume Levels -> System Sounds -> 100%
- Settings -> Sound -> Input -> Volume -> 100%
- Settings -> Keyboard -> Input Sources -> Add an Input Source -> Other -> Greek -> Add
- Settings -> Keyboard -> Keyboard Shortcuts -> Customize Shortcuts -> Navigation -> Hide all normal windows -> Settings -> Add a shortcut -> Super + D -> Set
- Settings -> Removable Media -> Software -> Ask what to do

# Configure Tweaks

_Tweak the GNOME Shell_

```shell
sudo apt install -y gnome-tweaks chrome-gnome-shell
```

- Tweaks -> Keyboard & Mouse -> Keyboard -> Show Extended Input Sources -> On
- Tweaks -> Keyboard & Mouse -> Mouse -> Acceleration Profile -> Flat
- Tweaks -> Top Bar -> Clock -> Weekday -> On
- Tweaks -> Top Bar -> Clock -> Seconds -> On
- Tweaks -> Top Bar -> Calendar -> Week Numbers -> On

```shell
reboot
```

# Install web apps and clients

_Every day apps_

```shell
sudo snap install skype --classic
wget https://download.teamviewer.com/download/linux/teamviewer_amd64.deb
sudo apt install -y ./teamviewer_amd64.deb
rm teamviewer_amd64.deb
```

- [Chrome](https://www.google.com/chrome/)
- [Discord](https://discord.com/download)
- [Zoom](https://zoom.us/download)

# Configure Extensions

_Install and configure GNOME extensions_

Use Chrome to install Dash to dock, Transparent top bar (adjustable transparency)

- Extensions -> Dash to dock -> Settings -> Launchers -> Move the applications button at the beggining of the dock.
- Extensions -> Dash to dock -> Settings -> Behavior -> Click action  -> Minimize or show previews
- Extensions -> Dash to dock -> Settings -> Behavior -> Scroll action  -> Cycle through windows
- Extensions -> Dash to dock -> Settings -> Appearance -> Shrink the dash -> Off
- Extensions -> Dash to dock -> Settings -> Appearance -> Customize windows counter indicators -> Dots
- Extensions -> Dash to dock -> Settings -> Appearance -> Customize windows counter indicators -> Settings -> Use dominant color -> On
- Extensions -> Dash to dock -> Settings -> Appearance -> Customize opacity -> Fixed
- Extensions -> Dash to dock -> Settings -> Appearance -> Opacity -> 0%
- Extensions -> Dash to dock -> Settings -> Appearance -> Force straight corner -> On
- Extensions -> Transparent top bar (adjustable transparency) -> Settings -> Top bar opacity -> 0%

# Configure the Desktop

_Customize the desktop settings_

- Desktop -> Desktop Icons Settings -> Size for the desktop icons -> Small
- Desktop -> Desktop Icons Settings -> Show the trash icon in the desktop -> On
- Desktop -> Desktop Icons Settings -> Show external drives in the desktop -> On
- Desktop -> Desktop Icons Settings -> Show network drives in the desktop -> On
- Desktop -> Desktop Icons Settings -> Show hidden files -> On
- Nautilus -> Preferences -> Optional Context Menu Actions -> Create Link -> On
- Nautilus -> Preferences -> Optional Context Menu Actions -> Delete Permanently -> On
- Nautilus -> Preferences -> Trash -> Show action to permanently delete files and folders -> On

# Enable firewall

_Enable the system firewall and install utility app_

```shell
sudo apt install -y gufw
sudo ufw enable
```

# Add proprietary codec/font support

_To properly handle more media formats_

```shell
sudo apt install -y ubuntu-restricted-extras
```

# Install package managers and image managers

_More package managers to gain access to more packages_

```shell
sudo apt install -y flatpak gnome-software-plugin-flatpak
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
sudo add-apt-repository ppa:appimagelauncher-team/stable
sudo apt install -y curl apt-transport-https
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install -y appimagelauncher docker-ce docker-ce-cli containerd.io
reboot
```

# Add media players

_When Totem doesn't quite cut it_

```bash
sudo apt install -y vlc rhythmbox
```

# Install IDEs

_Jetbrain IDEs ftw_

```bash
sudo snap install clion --classic
sudo snap install datagrip --classic
sudo snap install pycharm-professional --classic
sudo snap install webstorm --classic
```

# Install development tools

_Tools of the job_

```bash
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
rm -f packages.microsoft.gpg
sudo apt update
sudo apt install -y build-essential binutils flex bison gdb 
sudo apt install -y gh cmake ninja-build valgrind nasm code vim
sudo apt install -y texlive-latex-extra nodejs npm mysql-server
sudo apt install -y python3 python-is-python3 python3-dev python3-pip
```

# Configure MySQL Server

_This will haunt you_

```shell
sudo mysql_secure_installation
```

Set root password and accept all the other options. Now login as root:

```shell
sudo mysql -u root -p
```

As root now perform the following queries in order to create a new user account with root privileges:

```
CREATE USER 'name'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'name'@'localhost' WITH GRANT OPTION;
FLUSH PRIVILEGES;
EXIT
```

Now you can login through your create account which can also be used for connections:

```shell
mysql -u name -p
```

# Configure git

_Add ssh and gpg keys and use them with git, along with other settings_

```shell
git config --global user.name "insert name here"
git config --global user.email "insert email here"
git config --global user.username "insert username here"
git config --global core.editor code
git config --global help.autocorrect 0
git config --global user.signingkey "key here without quotes"
git config --global commit.gpgSign true
git config --global color.ui auto
```

# Install terminal utilities

_Useful everyday utilities_

```shell
sudo apt install -y clinfo ffmpeg htop cpu-checker zsh fish neofetch
sudo curl -L https://yt-dl.org/downloads/latest/youtube-dl -o /usr/local/bin/youtube-dl
sudo chmod a+rx /usr/local/bin/youtube-dl
```

# Install media production applications

_Back in business_

```shell
sudo add-apt-repository ppa:obsproject/obs-studio
sudo add-apt-repository ppa:inkscape.dev/stable
sudo apt update
sudo apt install -y obs-studio inkscape audacity blender gimp
```

# Install virtualization software

_OS in a box_

```bash
sudo apt install -y qemu qemu-kvm libvirt-daemon libvirt-clients bridge-utils virt-manager
sudo systemctl enable --now libvirtd
sudo usermod -aG libvirt $USER
sudo usermod -aG kvm $USER
reboot
```

# Install gaming apps

_Compatibility layers and gaming clients_

```bash
sudo dpkg --add-architecture i386
wget -nc https://dl.winehq.org/wine-builds/winehq.key
sudo apt-key add winehq.key
sudo add-apt-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ impish main'
sudo add-apt-repository ppa:lutris-team/lutris
sudo apt update
sudo apt install -y --install-recommends winehq-stable
sudo apt install -y steam lutris
```

# Wrap up

_Clean up and enjoy_

- Add to favourites: Chrome, Nautilus, Terminal, Gedit, Rhythmbox, Clion, DataGrip, Pycharm, Webstorm, Code, Steam, Discord

```bash
sudo apt autoremove -y
reboot
```

