# Genesis

Genesis will setup your Macbook from scratch

## How to install

```
curl -fsSL https://raw.githubusercontent.com/bangthetable/genesis/master/start | ruby
```
The above command will prompt for installing xcode-select, after that installs, enter the password and continue with the script.
This script will clone the genesis repo into `/tmp/genesis` and then run it for you.

For some reson if it fails and you need to run the script again, you can run it with the follwoing command:

```
cd /tmp/genesis
ansible-playbook -K mac.yml
```

## What it installs

### Terminal Utilities
- vim
- git
- fzf
- the_silver_searcher
- zsh
- z
- dnsmasq
- OhMyZsh

### Applications
- Chrome
- Firefox
- Slack
- Iterm2
- Sublime Text 3
- Alfred 3
- Docker edge

## After installation
- Setup ssh
- Make changes to the gitconfig added
