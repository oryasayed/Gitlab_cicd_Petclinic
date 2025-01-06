steps for creating CICD Pipelines

Ubuntu VM LTS
t2.medium


<img width="557" alt="image" src="https://github.com/user-attachments/assets/594a4b6b-0539-43f2-9f8f-9954acabe3d7" />

attach the pem file.

<img width="515" alt="image" src="https://github.com/user-attachments/assets/805c8448-ce7a-4591-a601-1e4e82ea3d2c" />


<img width="654" alt="image" src="https://github.com/user-attachments/assets/3f88c61b-3865-41e0-a7f0-8221ea791580" />

in MAC you connect from terminL


use this command 


# Install Docker

#  Update the System

sudo apt update && sudo apt upgrade -y

# Install Required Packages

sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

 # Add Docker’s Official GPG Key

#curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
#  Add Docker Repository

echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
#  Install Docker

sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io
#  Verify Docker Installation

docker --version
#  Install JDK
Install OpenJDK

sudo apt install -y openjdk-11-jdk
#  Verify JDK Installation

java -version

#  Install Maven

sudo apt install -y maven
#  Verify Maven Installation

mvn -version


# Configure GitLab Runner to Use Docker
 Install GitLab Runner
If not already installed, follow these steps:


curl -L https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh | sudo bash
sudo apt-get install gitlab-runner -y
# Register the Runner with Docker Executor

Run the following command to register the runner:

sudo gitlab-runner register
During the registration, choose:

Executor: docker
# Docker Image: For Java/Maven projects, use:
maven:3.8.7-openjdk-11

# after the registration enter
https://gitlab.com/

Enter the registration token
Copy the runner registration token from your GitLab project:

Go to your GitLab project.Navigate to Settings > CI/CD > Runners > Specific Runners.

Copy the registration token and paste it when prompted


<img width="882" alt="image" src="https://github.com/user-attachments/assets/e6022fe0-23d8-453f-be02-6bcb7c452c68" />




<img width="488" alt="image" src="https://github.com/user-attachments/assets/b9cef582-12f8-4393-a809-cba51fde0c3d" />

<img width="680" alt="image" src="https://github.com/user-attachments/assets/6a6b7d0c-7218-41f3-81cd-2f7f366d01b1" />


<img width="1156" alt="image" src="https://github.com/user-attachments/assets/eaf8a9c0-58c0-4ed3-8d26-7a1796824a23" />


the runner now added.


# now we are creating pipeline

<img width="524" alt="image" src="https://github.com/user-attachments/assets/416d847a-deed-417d-bddc-acc769f4ca88" />


creating the CI just few steps to check each step now we do compile only.

<img width="1136" alt="image" src="https://github.com/user-attachments/assets/3ed22961-89e7-4321-9b34-40f6a4b747fe" />

# we should install sonar

docker run -d --name sonar -p 9000:9000 sonarqube:lts-community


open 9000 port

create user
go to admin>security>user and generate token


<img width="1307" alt="image" src="https://github.com/user-attachments/assets/b7c029fb-eef9-4f04-8f01-db736b6c41bf" />

# sonar stage

<img width="1119" alt="image" src="https://github.com/user-attachments/assets/c9fb32c1-a9ad-4cd5-8f7a-ee5b7682c332" />





