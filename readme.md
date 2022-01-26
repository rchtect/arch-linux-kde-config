# Arch Linux (KDE) setup

(open terminal in the folder)

(./extra/dotfiles for the dotfiles configuration)

## **Installing nvidia drivers:**

`sudo pacman -S nvidia-installer-dkms`

`sudo pacman -S linux-lts-headers`

`sudo nvidia-installer-dkms`

`xrandr --output HDMI-0 --dpi 96`

`sudo systemctl reboot`

`sudo cp ./xorg.conf /etc/X11/`

`sudo chmod a+x ./kwin.sh`

`mkdir ~/.config/plasma-workspace ~/.config/plasma-workspace/env`

`sudo cp ./kwin.sh ~/.config/plasma-workspace/env/`

**Choosing Linux instead of Linux-LTS in GRUB**

`sudo nano /etc/default/grub`

`sudo grub-mkconfig -o /boot/grub/grub.cfg`

**Installing common cli stuff**

`yay -S git npm curl flatpak timeshift-bin`

**Installing Fonts**

`sudo cp ./.fonts/* ~/`

`sudo cp ./.fonts.conf ~/.fonts.conf`

`sudo fc-cache -fv`

(Enable SF Pro in settings)

**Installing patched JetBrains Mono font**

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/JetBrains/JetBrainsMono/master/install_manual.sh)"`

**Installing oh my zsh + p10k + plugins**

`yay -S zsh`

`sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`

`git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k`

`sudo git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`

`sudo cp ./.zshrc ~/.zshrc`

**Setting up Konsole**

`cp ./Dracula.colorscheme ~/.local/share/konsole`

`cp ./Profile1.profile ~/.local/share/konsole/`

`curl https://raw.githubusercontent.com/scopatz/nanorc/master/install.sh | sh`

`pacman -S nano-syntax-highlighting`

`echo "include ~/.nano/*.nanorc" >> ~/.nanorc`

`su`

`echo "include /usr/share/nano-syntax-highlighting/*.nanorc" >> /etc/nanorc`

(If nano syntax doesn't work correctly check: [Improved Nano Syntax Highlighting Files](https://github.com/scopatz/nanorc))

**Setting up KDE**

Install monterey + whitesur global themes

Install whitesur gtk theme

`yay -R dolphin`

`yay -S nautilus`

`git clone https://github.com/vinceliuice/WhiteSur-gtk-theme.git ./`

`cd ./WhiteSur-gtk-theme`

`./install.sh`

`./install.sh -N mojave`

`./tweaks.sh -f monterey`

`cd ../`

**Setting up layout**

`yay -S ulauncher latte-dock`

Make ulauncher trigger by super key

Change window behaviour > window actions to alt key

Remove panel

`git clone https://github.com/dracula/ulauncher.git ~/.config/ulaunc  
her/user-themes/dracula-ulauncher`

Import `latteconfig.layout.latte` file in Latte program

(If global menu wont run use: yay -S appmenu-gtk-module-git)

**Installing my preferred applications**

`yay -S discord visual-studio-code-bin wine winetricks github-desktop-bin element-desktop obsidian`

`wine /path/to/flstudio`

(Install ublock origin, bitwarden and remove uneeded browser configs)

(Sync vscode)

# Done :)
