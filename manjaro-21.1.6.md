# Update packages

_Updates your system applications_

```shell
sudo pacman -Syu
```

# Configure Settings

_Change the system settings_

- System Settings -> Appearance -> Global Theme -> Breath2 2021 Dark
- System Settings -> Workspace -> Workspace Behavior -> General Behavior -> Clicking in scrollbar track -> Scrolls to the clicked location
- System Settings -> Workspace -> Workspace Behavior -> Screen Locking -> Lock Screen automatiically -> Off
- System Settings -> Workspace -> Startup and Shutdown -> Autostart -> Manjaro Hello
- System Settings -> Workspace -> Startup and Shutdown -> Background Services -> Bluetooth -> Off
- System Settings -> Hardware -> Input Devices -> Keyboard -> Layouts -> Add -> Greek
- System Settings -> Hardware -> Input Devices -> Keyboard -> Layouts -> Shortcuts for Switching Layout -> Main shortcuts -> Super + Space
- System Settings -> Hardware -> Input Devices -> Mouse -> Acceleration Profile -> Flat
- System Settings -> Hardware -> Display and Monitor -> Compositor -> Rendering Backend -> OpenGL 3.1
- System Settings -> Hardware -> Audio -> Speaker Volume -> 100%
- System Settings -> Hardware -> Audio -> Microphone Volume -> 100%
- System Settings -> Hardware -> Audio -> Microphone -> Mute
- Manjaro News -> Settings -> Autostart -> Off
- Pamac -> Preferences -> Third Party -> Enable AUR Support -> On
- Pamac -> Preferences -> Third Party -> Enable Flatpak Support -> On
- Pamac -> Preferences -> Third Party -> Flatpak -> Check for updates -> On
- Pamac -> Preferences -> Third Party -> Enable Snap Support -> On

# Install terminal utilities

_Nice distractions_

```shell
sudo pacman -S neofetch xclip cmatrix
```

# Install development tools

_Tools of the job_

```bash
sudo pacman -S base-devel gdb
sudo pacman -S cmake ninja valgrind nasm vim
sudo pacman -S texlive-most nodejs npm
```

- Add docker
- Add mariadb and configure it

# Install IDEs

_Jetbrain IDEs ftw_

```bash
sudo snap install code --classic
sudo snap install clion --classic
sudo snap install datagrip --classic
sudo snap install pycharm-professional --classic
sudo snap install webstorm --classic
```

# Install web apps and clients

_Every day apps_

```shell
sudo snap install skype --classic
```

- [Chrome](https://aur.archlinux.org/packages/google-chrome/)
- [Zoom](https://zoom.us/download)

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

# Install virtualization software

_OS in a box_

```bash
sudo apt install -y qemu qemu-kvm libvirt-daemon libvirt-clients bridge-utils virt-manager
sudo systemctl enable --now libvirtd
sudo usermod -aG libvirt $USER
sudo usermod -aG kvm $USER
reboot
```

# Wrap up

_Clean up and enjoy_

- Add to favourites: Chrome, Nautilus, Terminal, Gedit, Rhythmbox, Clion, DataGrip, Pycharm, Webstorm, Code, Steam, Discord

```bash
sudo apt autoremove -y
reboot
```

