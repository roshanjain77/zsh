# zsh Configuration

Modern zsh configuration with Prezto and Powerlevel10k theme.

**Supported Platforms:** Linux and macOS (not tested on Windows)

**Requirements:**
- Git folder should be in your home directory
- macOS: Homebrew installed
- Anaconda/Conda (optional, but pre-configured)
- NVM (optional, but pre-configured)

## Setup Overview

1. Install zsh
2. Backup and remove existing zsh configs
3. Create symlinks to dotfiles
4. Set zsh as default shell (Linux only - macOS already uses zsh)
5. Install Nerd Font for icons
6. Configure terminal font and size
7. Configure conda and reload shell

---

## Installation Steps

### Step 1: Install zsh
```bash
# Linux
sudo apt install zsh

# macOS (zsh is pre-installed, but you can update it)
brew install zsh
```

### Step 2: Backup Existing Configs

**IMPORTANT: Backup existing configs**
If you already have `.zshrc`, `.zprofile`, or other zsh config files in your home directory, back them up first:
```bash
# Check what configs exist
ls -la ~ | grep "^\.(zsh\|bash)"

# Backup if needed (optional - you can also just delete them)
cp ~/.zshrc ~/.zshrc.backup
cp ~/.zprofile ~/.zprofile.backup
```

The symlink commands below will replace these files. If you have important configurations (like conda, nvm, or custom PATH settings), make sure to merge them into the dotfiles before creating symlinks, or re-add them after setup.

### Step 3: Create Symlinks

Execute the following commands from your home directory (`~`):
```bash
# Remove existing config files that will conflict with symlinks
rm -f ~/.zshrc ~/.zprofile ~/.zshenv ~/.zlogin ~/.zlogout ~/.zpreztorc ~/.aliases

# Rename zsh directory to dotfiles
mv zsh dotfiles

# Create symlinks (must be executed from home directory)
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

**Note: You must execute all commands from the home directory (`~`).**

### Step 4: Set zsh as Default Shell (Linux only)

macOS already uses zsh as the default shell. For Linux users, run:
```bash
chsh -s $(which zsh)
```

---

## Post-Setup Configuration

### Step 5: Install Nerd Font (Required for Icons)

Install the Meslo Nerd Font for Powerlevel10k to display icons correctly:

```bash
brew install --cask font-meslo-for-powerlevel10k
```

### Step 6: Configure Terminal Font and Size

After installing the font, configure your terminal to use it:

**For Terminal.app:**
1. Open Terminal → Preferences (`Cmd+,`)
2. Go to Profiles tab
3. Click on Font button
4. Select **"MesloLGS NF"** (or "MesloLGM Nerd Font")
5. Set size to **14 or larger** for better readability

**For iTerm2:**
1. Open iTerm2 → Preferences (`Cmd+,`)
2. Go to Profiles → Text
3. Click on Font dropdown
4. Select **"MesloLGS NF"** (or "MesloLGM Nerd Font")
5. Set size to **14 or larger** for better readability

### Step 7: Enable Conda and Reload Shell

**Enable Conda Base Environment (Optional):**

If you use Anaconda and want the base environment to activate automatically:

```bash
conda config --set auto_activate_base true
```

**Reload Your Shell:**

After all configurations, reload your shell:

```bash
source ~/.zshrc
```

Or simply **restart your terminal** for all changes to take effect.

---

## Troubleshooting

- **Question marks (?) instead of icons:** Make sure you installed the Nerd Font and selected it in your terminal preferences
- **Conda doesn't work:** Reload your shell with `source ~/.zshrc` or restart the terminal
- **Homebrew commands don't work on Apple Silicon Mac:** Make sure `/opt/homebrew/bin` is in your PATH (this is handled automatically in the config)
- **Symlink errors:** Remove existing files first with `rm -f ~/.zshrc` etc.

---

## Features Included

✅ **Prezto framework** - Fast and feature-rich zsh configuration framework
✅ **Powerlevel10k theme** - Beautiful and highly customizable prompt
✅ **Fast syntax highlighting** - Real-time command syntax highlighting
✅ **Autosuggestions** - Fish-like command autosuggestions
✅ **Homebrew integration** - Auto-configured for both Intel and Apple Silicon Macs
✅ **Conda support** - Pre-configured Anaconda/Miniconda initialization
✅ **NVM support** - Node Version Manager ready to use
✅ **Useful aliases** - Common shortcuts for productivity
✅ **Vi key bindings** - Vim-style editing in the shell

Enjoy your supercharged terminal! 🚀

