pipeline {
    agent any

    environment {
        MAVEN_HOME = "/usr/share/maven"
    }

    options {
        timestamps() // Enables timestamps in console output
    }

    stages {
        stage('Checkout Code') {
            steps {
                script {
                    try {
                        checkout([
                            $class: 'GitSCM', 
                            branches: [[name: '*/main']], 
                            userRemoteConfigs: [[
                                url: 'https://github.com/hasan914/ansible-devops',
                                credentialsId: 'your-jenkins-credentials-id' // Replace with your Jenkins Git credentials ID
                            ]]
                        ])
                    } catch (err) {
                        echo "Git Checkout failed: ${err}"
                        error("Stopping pipeline execution")
                    }
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    try {
                        sh 'mvn clean package'
                    } catch (err) {
                        echo "Build failed: ${err}"
                        error("Stopping pipeline execution")
                    }
                }
            }
        }

        stage('Extract Maven Version') {
            steps {
                script {
                    try {
                        def mavenVersion = sh(
                            script: 'mvn -version | grep "Apache Maven" | cut -d " " -f 3',
                            returnStdout: true
                        ).trim()
                        echo "Maven Version: ${mavenVersion}"
                    } catch (err) {
                        echo "Failed to extract Maven version: ${err}"
                        error("Stopping pipeline execution")
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    try {
                        sh 'ansible-playbook -i inventory.ini deploy.yml'
                    } catch (err) {
                        echo "Deployment failed: ${err}"
                        error("Stopping pipeline execution")
                    }
                }
            }
        }
    }

    post {
        always {
            echo "Pipeline execution completed."
        }
        success {
            echo "Pipeline executed successfully!"
        }
        failure {
            echo "Pipeline execution failed. Please check logs."
        }
    }
}
