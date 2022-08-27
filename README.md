# zsh

These configurations are only for Linux and Mac users. I don't know if they work on windows.

**Git folder should be in your home directory**.

Install zsh
```
sudo apt install zsh
```

Execute the following commands (home directory)
```
mv zsh dotfiles
ln -s dotfiles/zsh/.zprezto/ .zprezto
ln -s dotfiles/zsh/.zsh/ .zsh
ln -s dotfiles/zsh/.p10k.zsh .p10k.zsh
ln -s .zprezto/runcoms/zlogin .zlogin
ln -s .zprezto/runcoms/zlogout .zlogout
ln -s .zprezto/runcoms/zpreztorc .zpreztorc
ln -s .zprezto/runcoms/zprofile .zprofile
ln -s .zprezto/runcoms/zshenv .zshenv
ln -s .zprezto/runcoms/zshrc .zshrc
ln -s dotfiles/.aliases .aliases
```
**Note: You must execute commands from the home directory**.

The above commands may give errors if you already have a .zshrc file or any other file. Delete the files on which error was found (use rm command).


To make zsh default:
```
chsh -s $(which zsh)
```
Restart your device.


You may need to install [these](https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k) fonts. After installing the fonts, change the font preferences of your terminal to `MesloLGS NF`

