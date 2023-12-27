pipeline{
    agent any
    tools {
        maven 'maven'
    }
    stages{
        stage('SCM Checkout'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/chaithra0317/java-maven-war-app.git']])
            }
        }
        stage('Maven-Build'){
            steps{
                sh 'mvn clean install'
            }
        }
        stage('Sonar Scan'){
            steps{
                 withSonarQubeEnv("Sonar") {
                     sh "${tool("Sonar_4.8")}/bin/sonar-scanner \
                      -Dsonar.projectKey=java-maven-app"
                 }
             }
        }
        stage('deployment'){
            steps{
               
        }

    }
}
