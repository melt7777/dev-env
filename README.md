# env-melt-dev
my env setup for dev environment



### install system packages and fonts

```bash
sudo apt update; apt upgrade
sudo apt install build-essential locate nfs-common golang-go perl jsonlint vim git curl unzip ssh-askpass gnupg net-tools fontconfig zsh apt-transport-https libasound2 libx11-xcb1
sudo fc-cache -vf ~/.local/share/fonts/

# install my shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k

# copy files in 
~/.gitconfig
~/.bashrc
~/.zshrc
~/.local/share/fonts
~/.vscode
```

### .zshrc contains: 

```bash
export TERM="xterm-256color"
export DISPLAY=10.0.0.7:0
export GOPATH=/mnt/nfs/melt/r/code/pimp3-software:/mnt/nfs/melt/r

source ~/.local/share/fonts/*.sh
POWERLEVEL9K_PROMPT_ADD_NEWLINE=true
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(ram time newline dir_joined vcs)
POWERLEVEL9K_VCS_GIT_HOOKS=(vcs-detect-changes git-untracked git-aheadbehind git-remotebranch g$
ZSH_THEME="powerlevel9k/powerlevel9k"
export UPDATE_ZSH_DAYS=90
```

### install vscode

```
curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /usr/share/keyrings/
sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'

sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install code # or code-insiders
```

