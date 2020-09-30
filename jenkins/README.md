# Jenkins

## Setup Jenkin

```bash
yum update
yum install wget
wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo
rpm --import https://pkg.jenkins.io/redhat/jenkins.io.key
yum install jenkins
service jenkins start
yum install java-1.8.0
service jenkins start
```

## Create GitHub webhook
You need to proxy real DNS to your localhost. Ngrok the best way to do this
`docker run -e TARGET_HOST=jenkins -e TARGET_PORT=8080 --link <jenkins-container-name>:jenkins gtriggiano/ngrok-tunnel`

1. Run container with ngrok
2. In Github setup webhook https:<ngrok-url>/github-webhook
3. In Jenkins job makr "GitHub hook trigger for GITScm polling"
