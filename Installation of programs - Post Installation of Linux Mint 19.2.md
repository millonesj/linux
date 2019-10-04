# Post installation of Linux Mint 19.2
## Installation of programs  
* List of software:
  
  Visual Code  
  Fonts' Microsoft  
  Docker  and Docker Compose  
  Clementine  
  Git  
  Git-core  
  Vim  
  zsh  
  Htop  
  Snap  
  Tusk  
  filezilla  
  Tilix  
  Brave-browser  


* USE

  Copy this script.  
  Open terminal and paste it
```sh
sudo apt-get update && sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  && echo -e "\ndeb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable" | sudo tee -a /etc/apt/sources.list && curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg && sudo install -o root -g root -m 644 microsoft.gpg /etc/apt/trusted.gpg.d/ && sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list' && sudo apt-get update && sudo apt-get install -y  docker.io docker-compose gnupg-agent  software-properties-common code clementine git git-core snapd zsh vim tilix filezilla htop ttf-mscorefonts-installer && sudo groupadd docker && sudo usermod -aG docker $USER && sudo apt -y autoremove && sudo snap install tusk 

sudo apt install python3-pip \
sudo apt install python-pip \

sudo usermod -aG docker $USER \

sudo snap install teams-for-linux \
sudo snap install slack --classic \

curl -s https://brave-browser-apt-release.s3.brave.com/brave-core.asc | sudo apt-key --keyring /etc/apt/trusted.gpg.d/brave-browser-release.gpg add - \
source /etc/os-release \
echo "deb [arch=amd64] https://brave-browser-apt-release.s3.brave.com/ $UBUNTU_CODENAME main" | sudo tee /etc/apt/sources.list.d/brave-browser-release-${UBUNTU_CODENAME}.list \
sudo apt update \
sudo apt install -y brave-browser \
sudo apt -y autoclean \

wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh \
chsh -s `which zsh` \

```
