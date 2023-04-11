pipeline{

    agent any
    stages{
        stage('Static code analysis'){
            agent{
                docker{
                    image 'maven'
                }
            }
            steps{
                
                script{

                    withSonarQubeEnv(credentialsId: 'sonar-token'){
                        sh 'mvn clean package sonar:sonar'
                    }

                }
            }
        }
    }

    
}