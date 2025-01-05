steps for creating CICD Pipelines

Ubuntu VM LTS
t2.medium


<img width="557" alt="image" src="https://github.com/user-attachments/assets/594a4b6b-0539-43f2-9f8f-9954acabe3d7" />

attach the pem file.

<img width="515" alt="image" src="https://github.com/user-attachments/assets/805c8448-ce7a-4591-a601-1e4e82ea3d2c" />


<img width="654" alt="image" src="https://github.com/user-attachments/assets/3f88c61b-3865-41e0-a7f0-8221ea791580" />

use this command 

--- JDK & Maven Installation ---

sudo apt-get update -y
sudo apt install openjdk-11-jre -y
sudo apt-get install maven -y

--- Docker Installation ---

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg

sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  
  sudo apt-get update
  
  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
  
service docker restart
sudo usermod -aG docker $USER
newgrp docker
sudo chmod 666 /var/run/docker.sock
sudo systemctl restart docker



------!! IMPORTANT !!---BEFORE RUNNING FIRST PIPELINE ,RUN BELOW COMMAND-----

sudo rm /home/gitlab-runner/.bash_logout



