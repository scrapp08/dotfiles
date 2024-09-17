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
```

4. Install Homebrew, followed by the software listed in the Brewfile.

```zsh
# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Then pass in the Brewfile location...
brew bundle --file ~/.dotfiles/Brewfile

# ...or move to the directory first.
cd ~/.dotfiles && brew bundle
```

