pipeline {
  agent {
    docker {
      image 'maven:3.3.9-jdk-8'
      args '-v C:\\Users\\d.messina\\.m2:root\\.m2'
    }

  }
  stages {
    stage('initialize') {
      steps {
        sh '''echo PATH = ${PATH}
echo M2_HOME = ${M2_HOME}
mvn clean'''
      }
    }
    stage('Build') {
      steps {
        sh 'mvn install'
      }
    }
    stage('Report JUnit') {
      steps {
        junit '/target/surefire-reports/*'
      }
    }
  }
}