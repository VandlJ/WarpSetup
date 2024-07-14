# Warp Terminal Setup Guide

This guide will help you set up [Warp Terminal](https://www.warp.dev) on your Macbook with a personalized configuration that includes several useful plugins. Follow the steps below to get started.

## Step 1: Install a Nerd Font

First, you need to install a font that supports special icons. You can choose from a variety of fonts at [Nerd Fonts](https://www.nerdfonts.com/font-downloads). For example, you can download and install "Hack Nerd Font".

## Step 2: Install Oh-My-Zsh

Install [Oh-My-Zsh](https://ohmyz.sh/#install) using one of the following commands:

Via curl:
```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Via wget:
```sh
sh -c "$(wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
```

## Step 3: Install Powerlevel10k Theme

Clone the [Powerlevel10k](https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#oh-my-zsh) repository:
```sh
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

Open your `.zshrc` file with a text editor (nvim, nano, etc.) and set the theme:
```sh
ZSH_THEME="powerlevel10k/powerlevel10k"
```

After making changes to .zshrc, source the file:
```sh
source .zshrc
```

A configuration wizard should start automatically. If not, run:
```sh
p10k configure
```

## Step 4: Install Additional Oh-My-Zsh Plugins

### Zsh Syntax Highlighting

Clone the [Zsh syntax highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md) plugin repository:
```sh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
### Zsh Autosuggestions

Clone the [Zsh autosuggestions](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh) plugin:
```sh
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

Edit your .zshrc file to include these plugins:
```sh
plugins=(git zsh-syntax-highlighting zsh-autosuggestions)
```

Source the .zshrc file again:
```sh
source .zshrc
```

## Step 5: Install Colorls

Install the [colorls](https://github.com/athityakumar/colorls?tab=readme-ov-file#installation) plugin using `gem`:
```sh
sudo gem install colorls
```

If you encounter error that looks like this:
```sh
ERROR:  Error installing colorls:
	The last version of public_suffix (>= 2.0.2, < 7.0) to support your Ruby & RubyGems was 5.1.1. Try installing it with `gem install public_suffix -v 5.1.1` and then running the current command again
	public_suffix requires Ruby version >= 3.0. The current ruby version is 2.6.10.210.
```

Try solving it by updating `public_suffix` with this command:
```sh
sudo gem install public_suffix -v 5.1.1
```

Then re-run the installation of colorls:
```sh
sudo gem install colorls
```

Set an alias for colorls by adding the following line to your .zshrc file:
```sh
alias ls='colorls'
```

Source the .zshrc file one last time:
```sh
source .zshrc
```

## Conclusion

After completing these steps, you should have a fully configured Warp Terminal with the best settings and plugins. Enjoy your new setup!