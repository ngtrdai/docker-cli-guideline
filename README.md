# Install Docker CLI in WSL2 Guideline
## Instal WSL2
- [Install WSL2](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

## Install Distribution
- [Install Ubuntu](https://docs.microsoft.com/en-us/windows/wsl/install-win10#install-your-linux-distribution-of-choice)

## Install Docker CLI

1. Update the apt package index and install packages to allow apt to use a repository over HTTPS:
```bash
sudo apt-get update &&
sudo apt-get install -y \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common \
    libssl-dev \
    libffi-dev \
    git \
    wget \
    nano
```

2. Add group docker
```bash
sudo groupadd docker
```

3. Add user to group docker
```bash
sudo usermod -aG docker $USER
```

4. Install Docker CLI
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - &&
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable" &&
sudo apt-get update &&
sudo apt-get upgrade -y &&
sudo apt-get autoremove -y &&
sudo apt-get install -y docker-ce docker-ce-cli containerd.io
```

5. Auto start docker
```bash
echo "sudo service docker start" >> ~/.profile
```

6. Install Docker Compose
```bash
sudo apt-get install -y docker-compose
```
