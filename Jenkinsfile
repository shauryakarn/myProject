pipeline {
  agent {label 'linux01'}
  tools {
    maven 'M3'
  }
  stages {
    stage('Checkout from github'){
      steps{
        git 'https://github.com/shauryakarn/myProject.git'
      }
    }
    stage('Build'){
      steps{
        sh 'mvn clean compile'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('package'){
      steps{
        sh 'mvn package'      
      }
    }
  }
}