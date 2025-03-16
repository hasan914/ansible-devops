pipeline {
    agent any
    stages{
        stage('Docker Node Version'){
            steps{
                script{
                    docker.image('node:14').inside{
                        sh 'node -v'
                        echo "Hasan Javed"
                    }
                }
            }
        }
        stage('Docker Maven Version'){
            steps{
                script{
                    docker.image('maven:3.8.1').inside{
                        sh 'mvn -v'
                        echo "Hasan JAved"
                    }
                }
            }
        }
    }
}