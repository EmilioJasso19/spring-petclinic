#!groovy

pipeline {
  agent any
  stages {
    stage('Maven Install') {
      agent {
        docker {
          image 'maven:3.9.6',
          args '-v $WORKSPACE:/app'
        }
      }
      steps {
        sh 'mvn clean install -X'
      }
    }
    stage('Docker Build') {
      steps {
        sh 'docker build -t emiliojasso19/spring-petclinic:latest .'
      }
    }
  }
}
