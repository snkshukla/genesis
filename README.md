# Genesis

Genesis will setup your Macbook from scratch or alternatively setup only the machine networking to get the apps running locally.

## How to install

### Setup your mac from scratch (Installs developer utilities/tools and the sets up the required machine networking)
Run: ```
curl -fsSL https://raw.githubusercontent.com/bangthetable/genesis/master/start | ruby```

### Setup only the required machine networking
Run: ```curl -fsSL https://raw.githubusercontent.com/bangthetable/genesis/master/start | ruby - NETWORKING_ONLY=true```


### Command line arguments you can pass to the script:
 - `NETWORKING_ONLY=true/false` : If set to `true` (Default value is `false`) installs only the required machine networking. Please note that this is the <strong> absolute minimum setup</strong> that you need to make BTT's apps run locally. If this is not installed/setup properly <strong>the apps won't run locally.</strong>

PS: The first argument passed to the ruby interpretor here is `-`, this is necessary to let ruby know that the source is `STDIN`.

The above commands will prompt for installing xcode-select, after that installs, enter the password and continue with the script.
This script will clone the genesis repo into `/tmp/genesis` and then run it for you.

## After the install
 - Please reboot your system to let dnsmasq start.
 - Assuming that everything installed correctly, running: `dig dev.ehq.test @localhost` should give you the DNS A record answer `10.200.10.1`.

## Troubleshooting

1. Ansible fails due to errors relating to sudo/password or any other error:

Rerun the script with the following command(-K is for `--ask-become-pass`):
```
cd /tmp/genesis
ansible-playbook -K mac.yml
```

2. Ansible fails because some utility/software was already installed:

  Make sure that you don't have anything pre-installed when running genesis.
  If you need to install something please ensure brew was used to install it or else the script will fail.

  If you did install something without homebrew, then please delete the software's name from the file, `mac.yml` and rerun the script.

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
