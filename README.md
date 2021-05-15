# zsh

Rename the git file as **dotfiles**.

Execute the following commands
```
ln -s dotfiles/zsh/.zprezto/ .zprezto
ln -s dotfiles/zsh/.zsh/ .zsh
ln -s dotfiles/zsh/.p10k.zsh .p10k.zsh
ln -s .zprezto/runcoms/zlogin .zlogin
ln -s .zprezto/runcoms/zlogout .zlogout
ln -s .zprezto/runcoms/zpreztorc .zpreztorc
ln -s .zprezto/runcoms/zprofile .zprofile
ln -s .zprezto/runcoms/zshenv .zshenv
ln -s .zprezto/runcoms/zshrc .zshrc
```

You may need to install [these](https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k) fonts. After installing the fonts, change font prefrences of your terminal to ~MesloLGS NF~

