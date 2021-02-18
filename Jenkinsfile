pipeline{
    agent any
    tools{
    maven "maven3"
    java "jdk11"
    }
    stages{
        stage('mvn clean'){
            steps{
                bat 'mvn compile'
            }
        }
        stage('build and sonarqube analysis'){
            steps{
                withSonarQubeEnv('sonar-server'){
                bat 'mvn package sonar:sonar'
                }    
            }
        }
        
    }
}
