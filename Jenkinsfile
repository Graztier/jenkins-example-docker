pipeline {
  agent any
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
  }
  stages {
    stage('git') {
      steps {
        git branch: 'main', url: 'https://github.com/Graztier/jenkins-example-docker.git'        
      } 
    }
    stage('scan') {
      steps {
        withSonarQubeEnv(installationName: 'sq1') {
          bat'./mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
        }
      }
    }
  }
}
