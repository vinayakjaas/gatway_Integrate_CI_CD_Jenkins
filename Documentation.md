# Documentation for CI/CD Integeration Using Jenkins

### Step 1: Launch an AWS EC2 Instance

- Log in to your AWS Management Console.
- Navigate to the EC2 dashboard.
- Click on "Launch Instance" to create a new EC2 instance.
- Choose an Amazon Machine Image (AMI) based on your preferences (e.g., Amazon Linux 2 AMI).

![Launch Instance](Images\AWS_EC2.jpg)
 SetUp EC2 Instances

![Launch Instance](Images\AWS_EC2_2.jpg)
EC2 IS Now Running 

![Launch Instance](Images\AWS_CONFIG.jpg)
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
![Launch Instance](Images\INSTALL_JENKINS.jpg)

![Launch Instance](Images\INSTALL_JENKINS_1.jpg)

### Step 3: Configuration Jenkins
- Run Jenkins On Port ```:8080```

![Launch Instance](Images\RUN_JENKINS_SERVER.jpg)

- Configure Jenkins

![Launch Instance](Images\JENKINS_CONFIGURATION.jpg)

- Build Jenkins

![Launch Instance](Images\BUILD_JENKINS.jpg)

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
![Launch Instance](Images\SETUP_DOCKER_FILE.jpg)

- Add GitHub Integeration In Plugins

![Launch Instance](Images\ADD_PLUGINS.jpg)

![Launch Instance](Images\GITHUB_INTEGERATION.jpg)

- Download GitHub Integeration And Restart The Server

![Launch Instance](Images\DOWNLOAD_GITHUB_INTEGERATION.jpg)

### Step 5: Add WebHook 

- Go To Repo Setting In Github And click on webhook

![Launch Instance](Images\ADD_GITHUB_WEBHOOK.jpg)

![Launch Instance](Images\ADD_GITHUB_WEBHOOK_1.jpg)

- Add Docker To Build Manually 
![Launch Instance](Images\ADD_DOCKER_TO_BUILD_MANULLY.jpg)











 




