pipeline {

agent any

environment {

APP_SERVER = "172.31.29.255"
}

stages {

stage('Checkout') {

steps {

git branch: 'main',
url: 'https://github.com/Ninad262002/jenkins-project-practice.git'
}
}

stage('Deploy Website') {

steps {

sshagent(['app-server-key']) {

sh """

scp \
index.html \
ubuntu@$APP_SERVER:/tmp/

ssh \
ubuntu@$APP_SERVER '

sudo cp /tmp/index.html \
/var/www/html/index.html

'

"""
}
}
}
}
}