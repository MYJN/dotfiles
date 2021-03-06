This repository holds my configuration files so that I can clone them to other machines
easily.

#Installation

    git clone git://github.com/PinkyJie/dotfiles.git ~/.dotfiles

#Setup
## Homebrew
On those Mac OS machines where I install Homebrew I also edit `/etc/paths` to move the `/usr/local/bin` entry to the top of the list. This ensures that Homebrew-managed programs and libraries occur prior to `/usr/bin` and system-provided programs and libraries. The resulting `/etc/paths` files looks like this:

    /usr/local/bin
    /usr/bin
    /bin
    /usr/sbin
    /sbin
    
## zsh
For zsh configuration create the following symlinks:

    ln -s ~/.dotfiles/zsh ~/.zsh
    ln -s ~/.dotfiles/zsh/zshrc ~/.zshrc
    ln -s ~/.dotfiles/zsh/zshenv ~/.zshenv
    ln -s ~/.dotfiles/zsh/zprofile ~/.zprofile

## oh-my-zsh
Install oh-my-zsh first:

    cd ~
    curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh

Our `.zshrc` file will be overwritten by oh-my-zh, we need to roll back our original one:

    mv .zshrc ~/.dotfiles/zsh/oh-my-zsh.zsh
    ln -s ~/.dotfiles/zsh/zshrc ~/.zshrc
    cp ~/.dotfiles/ohmyzsh/* ~/.oh-my-zsh/themes/

Cusomize oh-my-zsh configuration in `~/.dotfiles/zsh/oh-my-zsh.zsh`.
		
## ssh
For ssh configuration, create the following symlink:

    ln -s ~/.dotfiles/ssh/config ~/.ssh/config

## Git
For Git configuration and global ignore files, create these symlinks:

    $ ln -s ~/.dotfiles/git/gitconfig ~/.gitconfig
    $ ln -s ~/.dotfiles/git/gitignore_global ~/.gitignore_global

For machines where Sublime Text 2 cannot be installed, link
`git/gitconfig_remote` instead. This will use `vimdiff` as the merge and diff
tool rather than ST2.

## tmux (terminal multiplexer) configuration
For tmux configuration create this symlink:

    $ ln -s ~/.dotfiles/tmux/tmux.conf ~/.tmux.conf

## Sublime Text 2 (subl)
Install Package Control following the instructions here: http://wbond.net/sublime_packages/package_control

For Sublime Text 2 settings, remove the `User` directory from
`~/Library/Application Support/Sublime Text 2/Packages`. Then add this symlink:

    $ cd ~/Library/Application\ Support/Sublime\ Text\ 2/Packages
    $ ln -s ~/.dotfiles/sublimetext/User User

Finally, to enable the command line tool, `subl`, add this symlink:

    $ ln -s /Applications/Sublime\ Text\ 2.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl
    
## Atom
For Atom settings, remove the `.atom` directory from `~/`. Then add this symlink:

    $ ln -s ~/.dotfiles/atom ~/.atom

## aria2

    mkdir ~/.aria2
    $ ln -s ~/.dotfiles/aria2/aria2.conf ~/.aria2/aria2.conf

## proxychains
Use shadowsocks as proxy server:

    mkdir ~/.proxychains
    ln -s ~/.dotfiles/proxychains/proxychains.conf ~/.proxychains/proxychains.conf


