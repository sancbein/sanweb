pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '**']], extensions: [], userRemoteConfigs: [[credentialsId: '494342df-10c0-4dfd-b8e1-c9c5a4eb296d', url: 'https://github.com/sancbein/sanweb.git']]])
            }
        }
        stage('Build'){
            steps {
                git branch: '', changelog: false, credentialsId: '494342df-10c0-4dfd-b8e1-c9c5a4eb296d', poll: false, url: 'https://github.com/sancbein/sanweb.git'
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
