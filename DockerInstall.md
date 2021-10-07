#Ubuntu
#Install using the repository
#Paso 1.
apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

#Paso 2. Add Docker’s official GPG key:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
#Paso 3.
echo   "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu   $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

#Install Docker Engine
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io

docker --version

sudo groupadd docker
sudo usermod -aG docker v1kt0r
Sudo chmod 777 /var/run/docker.sock


#Configure Docker to start on boot

systemctl enable docker.service
systemctl enable containerd.service

#Configurar el acceso remoto con systemd unit file

1.Use the command sudo systemctl edit docker.service to open an override file for docker.service in a text editor
sudo systemctl edit docker.service

2.Add or modify the following lines, substituting your own values.

[Service]
ExecStart=
ExecStart=/usr/bin/dockerd -H fd:// -H tcp://127.0.0.1:2375

3.Save the file.

4.sudo systemctl daemon-reload

5.sudo systemctl restart docker.service

sudo netstat -lntp | grep dockerd