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


# Install development tools

_Tools of the job_

```bash
sudo apt update
sudo pacman -S build-essential binutils flex bison gdb 
sudo pacman -S cmake ninja-build valgrind nasm vim
sudo pacman -S texlive-latex-extra nodejs npm mysql-server
```

# Install IDEs

_Jetbrain IDEs ftw_

```bash
sudo snap install code --classic
sudo snap install clion --classic
sudo snap install datagrip --classic
sudo snap install pycharm-professional --classic
sudo snap install webstorm --classic
```
