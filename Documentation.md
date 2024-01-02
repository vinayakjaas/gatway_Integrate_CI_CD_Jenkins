# Documentation for CI/CD Integeration Using Jenkins

### Step 1: Launch an AWS EC2 Instance

- Log in to your AWS Management Console.
- Navigate to the EC2 dashboard.
- Click on "Launch Instance" to create a new EC2 instance.
- Choose an Amazon Machine Image (AMI) based on your preferences (e.g., Amazon Linux 2 AMI).

![Launch Instance](https://i.postimg.cc/KcNyKfpR/AWS-EC2.jpg)
 SetUp EC2 Instances

![Launch Instance](https://i.postimg.cc/XYhWjvHL/AWS-EC2-2.jpg)
EC2 IS Now Running 

![Launch Instance](https://i.postimg.cc/gktFsJWp/AWS-CONFIG.jpg)
Configure AWS EC2 Instances Locally (Linux(Ubuntu))

### Step 2: Install Jenkins

- Install Java  ``` sudo apt install openjdk-11-jre ```
- Java Version ``` java -version ```
-Jenkis Install
```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
![Launch Instance](https://i.postimg.cc/L5y7xyGD/INSTALL-JENKINS.jpg)

![Launch Instance](https://i.postimg.cc/MZthZTXB/INSTALL-JENKINS-1.jpg)

### Step 3: Configuration Jenkins
- Run Jenkins On Port ```:8080```

![Launch Instance](https://i.postimg.cc/d1jgyQBz/RUN-JENKINS-SERVER.jpg)

- Configure Jenkins

![Launch Instance](https://i.postimg.cc/QM52jJWN/JENKINS-CONFIGURATION.jpg)

- Build Jenkins

![Launch Instance](https://i.postimg.cc/vT3Rp8xW/BUILD-JENKINS.jpg)

### Step 4: Dcker Setup And GitHub Integeration

- Insatll Docker 
```
sudo apt install docker.io
FROM node:12.2.0-alpine
WORKDIR app
COPY . .
RUN npm install
EXPOSE 8000
CMD ["node","app.js"]
docker build . -t node-app
sudo usermod -a -G docker $USER
docker run -d --name node-todo-app -p 8000:8000 github-integeration

```
![Launch Instance](https://i.postimg.cc/zvD6Sm23/SETUP-DOCKER-FILE.jpg)

- Add GitHub Integeration In Plugins

![Launch Instance](https://i.postimg.cc/2yzRcLyk/ADD-PLUGINS.jpg)

![Launch Instance](https://i.postimg.cc/g2w9TWzZ/GITHUB-INTEGERATION.jpg)

- Download GitHub Integeration And Restart The Server

![Launch Instance](https://i.postimg.cc/tgxjYH8j/DOWNLOAD-GITHUB-INTEGERATION.jpg)

### Step 5: Add WebHook 

- Go To Repo Setting In Github And click on webhook

![Launch Instance](https://i.postimg.cc/XJK6kkV1/ADD-GITHUB-WEBHOOK.jpg)

![Launch Instance](https://i.postimg.cc/TwvXb4XW/ADD-GITHUB-WEBHOOK-1.jpg)

- Add Docker To Build Manually 
![Launch Instance](https://i.postimg.cc/TY4qC8NF/ADD-DOCKER-TO-BUILD-MANULLY.jpg)











 




