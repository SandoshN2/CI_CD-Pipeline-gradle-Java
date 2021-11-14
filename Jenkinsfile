pipeline{
    agent any
    stages{
        stage("Sonar Quality Check :"){
            agent {
                docker{
                    image 'OpenJDK:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'SonarQube-Token') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'
                    }
                }
            }
        }
    }
}