
# How to install, setup and config mysql in docker
* [Learn More](https://docs.docker.com/engine/install/ubuntu/)

# How to install docker

```bash
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker   containerd runc; do sudo apt-get remove $pkg; done
```

```bash 
sudo apt-get update
```

```bash
sudo apt-get install ca-certificates curl gnupg
```
```bash
sudo install -m 0755 -d /etc/apt/keyrings
```
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```
```bash
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```
### Add the repository to Apt sources ###
```bash
echo \
 "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```bash
sudo apt-get update
```
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
```bash
sudo groupadd docker
```
```bash
sudo usermod -aG docker $USER
```

```bash
newgrp docker
```
```bash
docker run hello-world
```
```bash
sudo systemctl enable docker.service
```
```bash
sudo systemctl enable containerd.service
```


# How to pull mysql into docker 
```bash
docker pull mysql
```
### Create a new directory to store the containers: ###
```bash
mkdir workspace
```
```bash
cd workspace/
```
```bash
mkdir mysql
```
```bash
cd mysql
```
### if not already installed vim and nano: ###
```bash
sudo apt install vim
```
```bash
sudo apt install nano
```
```bash
vim docker-compose.yaml
```

### paste this snippet and put a password in MYSQL_ROOT_PASSWORD: ###
version: '3.1'

services:

  db:
    image: mysql
    # NOTE: use of "mysql_native_password" is not recommended: https://dev.mysql.com/doc/refman/8.0/en/upgrading-from-previous-series.html#upgrade-caching-sha2-password
    # (this is just an example, not intended to be a production configuration)
    command: --default-authentication-plugin=mysql_native_password
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD:<your password>

  adminer:
    image: adminer
    restart: always
    ports:
      - 8080:8080


# install compose
```bash
sudo apt install docker-compose
```
```bash
docker-compose up -d
```

### to check what containers are running currently: ###
```bash
docker ps
```
### to check the configs of a particular container: ###
```bash
docker inspect <containerID>
```
### to check the IP of a particular container: ###
```bash
docker inspect <containerID> | grep IP
```
### this will enter you in a bash i.e your container ###
```bash
docker exec -it <your container id> /bin/bash
```
### to run mysql in cmd ###
```bash
mysql -u root -p
```
### to exit###
```bash
exit
```
