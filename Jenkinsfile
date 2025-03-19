pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/hasan914/ansible-devops'
            }
        }

        stage('Run Node.js & Show Version') {
            steps {
                script {
                    sh 'docker run --rm node:latest node -v'
                }
            }
        }

        stage('Run Maven & Show Version') {
            steps {
                script {
                    sh 'docker run --rm maven:latest mvn -version'
                }
            }
        }

        stage('Build with Maven') {
            steps {
                script {
                    def workspace = pwd()
                    sh "docker run --rm -v ${workspace}:/app -w /app maven:latest mvn clean package"
                }
            }
        }
    }
}
