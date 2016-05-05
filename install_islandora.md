# Install Islandora

## Vagrant Setup
*_OSX, Windows, Linux_*

### Setup on OS X
__Video: Open Terminal from within OS X__
[![Open Terminal](http://img.youtube.com/vi/zw7Nd67_aFw/0.jpg)](https://youtu.be/zw7Nd67_aFw)

#### Install brew, virtualbox, vagrant, and git

*From Terminal:*
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
## Setup on Windows
Follow these links and install the apps for your version of windows
1. [VirtualBox](https://www.virtualbox.org/)
2. [Vagrant](http://www.vagrantup.com)
3. [git](https://git-scm.com/)

Start >> Run >> cmd __OR__ Windows Key + R >> cmd
```bash
cd %USERPROFILE%\Desktop
git clone https://github.com/utkdigitalinitiatives/islandora_vagrant
cd islandora_vagrant
vagrant up
```


## Typical Daily Use
Note for Windows: replace ~/desktop with %USERPROFILE%\Desktop<br/>
To __Start__ Open Terminal
```bash
cd ~/desktop/islandora_vagrant
vagrant up
```

To __Stop__ when done using Islandora
Open Terminal
```bash
cd ~/desktop/islandora_vagrant
vagrant halt
```

To **Start-Over**, Open Terminal
```bash
cd ~/desktop/islandora_vagrant
vagrant halt
vagrant destroy
vagrant up
```

## Server Setup