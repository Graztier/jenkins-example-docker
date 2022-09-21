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
    stage('log') {
        sh "git log -n 1"
      }
    }
  }
}
