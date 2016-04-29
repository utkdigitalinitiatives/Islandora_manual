# Install Islandora

## Vagrant Setup OSX, Windows, Linux

**OSX:**
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew tap caskroom/cask
brew install brew-cask
brew cask install virtualbox
brew cask install vagrant
brew cask install vagrant-manager
brew install git
cd desktop
git clone https://github.com/utkdigitalinitiatives/islandora_vagrant
cd islandora_vagrant
vagrant up
```
**Windows:**
