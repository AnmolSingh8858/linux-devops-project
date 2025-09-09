pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/AnmolSingh8858/linux-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t linux-devops-app .'
            }
        }

        stage('Run Container') {
            steps {
                // Agar container pehle se run ho raha ho, stop & remove karo
                sh 'docker rm -f linux-devops-app || true'
                sh 'docker run -d --name linux-devops-app -p 8080:3000 linux-devops-app'
            }
        }
    }
}

