pipeline{
    agent any
    stages{
        stage("Sonar Quality Check :"){
            agent {
                docker{
                    image 'openjdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'Sonar-Jenkins-Intergration') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'
                    }
                }
            }
        }
    }
}
