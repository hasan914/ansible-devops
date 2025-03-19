pipeline {

    agent any

    stages {

        stage('Docker Node Version') {
            steps {
                script {
                    def node_version = sh(script: "docker run --rm --network jenkins_A4_network node:14 node -v", returnStdout: true).trim()
                    echo "Node.js Version: ${node_version} Hasan Javed"
                }
            }
        }

        stage('Docker Maven Version') {
            steps {
                script {
                    def maven_version = sh(script: "docker run --rm --network jenkins_A4_network maven:3.8.1 mvn -version | awk '/Apache Maven/ {print \\$3}'", returnStdout: true).trim()
                    echo "Maven Version: ${maven_version} Hasan Javed"
                }
            }
        }

    } // Closing stages

} // Closing pipeline
