pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/newbranch']], extensions: [], userRemoteConfigs: [[credentialsId: '494342df-10c0-4dfd-b8e1-c9c5a4eb296d', url: 'https://github.com/sancbein/hello-world.git']]])
            }
        }
        stage('Build'){
            steps {
                git branch: 'newbranch', credentialsId: '494342df-10c0-4dfd-b8e1-c9c5a4eb296d', url: 'https://github.com/sancbein/hello-world.git'
                sh 'javac Simple.java; java Simple'
            }
        }
        stage('Test'){
            steps {
                echo 'Testing application'
            }
        }
    }
}
