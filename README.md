# MacOS Dotfiles

1. Install Command Line Tools

```zsh
xcode-select --install
```

2. Clone repo into new hidden directory

```zsh
# Using HTTPS
git clone https://github.com/scrapp08/dotfiles.git ~/.dotfiles

# Using SSH
git clone git@github.com:scrapp08/dotfiles.git ~/.dotfiles
```

3. Create symlinks in the Home directory to the real files in the repo.

```zsh
ln -s ~/.dotfiles/.zshrc ~/.zshrc
ln -s ~/.dotfiles/.gitconfig ~/.gitconfig
ln -s ~/.dotfiles/.oh-my-zsh/ ~/.oh-my-zsh/
ln -s ~/.dotfiles/.p10k.zsh ~/.p10k.zsh
```

4. Install Homebrew, followed by the software listed in the Brewfile.

```zsh
# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Add Homebrew to path
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/ed/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"

# Then pass in the Brewfile location...
brew bundle --file ~/.dotfiles/Brewfile

# ...or move to the directory first.
cd ~/.dotfiles && brew bundle
```

5. Install remaining stuff
```zsh
# Oh My ZSH
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# PowerLevel10k (ZSH theme)
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k

# zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
