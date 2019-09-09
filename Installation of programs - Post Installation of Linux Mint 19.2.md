# Post installation of Linux Mint 19.2
## Installation of programs  
* List of software:
  
  Visual Code  
  Fonts' Microsoft  
  Docker  and Docker Compose  
  Clementine
  Git  
  Vim  
  Htop  
  Snap  
  Tusk


* USE

  Copy this script.  
  Open terminal and paste it
```sh
sudo apt-get update && sudo apt-get install apt-transport-https ca-certificates curl software-properties-common && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  && echo -e "\ndeb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable" | sudo tee -a /etc/apt/sources.list && curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg && sudo install -o root -g root -m 644 microsoft.gpg /etc/apt/trusted.gpg.d/ && sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list' && sudo apt-get update && sudo apt-get install  -y sudo apt install -y  docker.io docker-compose gnupg-agent  software-properties-common code clementine git snapd vim htop ttf-mscorefonts-installer && sudo snap install tusk && sudo groupadd docker && sudo usermod -aG docker $USER && sudo apt -y autoremove && sudo apt -y autoclean
```
