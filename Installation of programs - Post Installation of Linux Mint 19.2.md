# Post installation of Linux Mint 19.2
## Installation of programs  
* List of software:
  
  
  Brave-browser  
  Clementine  
  DBeaver  
  Docker  and Docker Compose  
  Filezilla  
  Flameshot  
  Fonts' Microsoft  
  Git  
  Git-core  
  Htop  
  Snap  
  Slack  
  Tusk  
  Tilix  
  Visual Code  
  Vim  
  Youtube-dl
  Notion
  Rofi
  zsh with oh-my-zsh  

* USE

  Copy this script.  
  Open terminal and paste it  
```sh
sudo apt-get update 
sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common 

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  && echo -e "\ndeb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable" | sudo tee -a /etc/apt/sources.list 
curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg 

sudo install -o root -g root -m 644 microsoft.gpg /etc/apt/trusted.gpg.d/ 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list' 

sudo add-apt-repository ppa:serge-rider/dbeaver-ce 

sudo apt-get update 
sudo apt-get install -y docker.io docker-compose gnupg-agent software-properties-common code clementine git git-core snapd zsh vim tilix filezilla htop ttf-mscorefonts-installer flameshot dbeaver-ce 
sudo groupadd docker && sudo usermod -aG docker $USER 
sudo usermod -aG docker $USER 

sudo apt install -y python3-pip 
sudo apt install -y python-pip 
sudo apt install -y rofi 

pip3 install youtube-dl 
python3 -m pip install localstack 

# INSTALL APPS WITH SNAP
sudo snap install slack --classic 
sudo snap install tusk 
sudo snap install notion-snap 

curl -s https://brave-browser-apt-release.s3.brave.com/brave-core.asc | sudo apt-key --keyring /etc/apt/trusted.gpg.d/brave-browser-release.gpg add - \
source /etc/os-release \ 
echo "deb [arch=amd64] https://brave-browser-apt-release.s3.brave.com/ $UBUNTU_CODENAME main" | sudo tee /etc/apt/sources.list.d/brave-browser-release-${UBUNTU_CODENAME}.list 
sudo apt update 
sudo apt install -y brave-browser 

wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh 
chsh -s `which zsh`

# INSTALL KUBECTL
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.23.0/bin/linux/amd64/kubectl 
chmod +x ./kubectl 
sudo mv ./kubectl /usr/local/bin/kubectl
kubectl version --client 

# INSTALL KIND
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.11.1/kind-linux-amd64 
chmod +x ./kind 
sudo mv ./kind /usr/local/bin/kind 

# INSTALL MINIKUBE 
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 
sudo install minikube-linux-amd64 /usr/local/bin/minikube 


# INSTALL STERN
curl -LO https://github.com/wercker/stern/releases/download/1.11.0/stern_linux_amd64
sudo install stern_linux_amd64 /usr/local/bin/stern 

# INSTALL KOMPOSE
curl -L https://github.com/kubernetes/kompose/releases/download/v1.25.0/kompose-linux-amd64 -o kompose 
chmod +x kompose 
sudo mv ./kompose /usr/local/bin/kompose 

# INSTALL NVM
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash

sudo apt -y autoremove 
sudo apt -y autoclean 

```
