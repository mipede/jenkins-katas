pipeline {
  agent {
    docker {
      image 'gradle:6-jdk11'
    }

  }
  stages {
    stage('Say Hello') {
      parallel {
        stage('Say Hello') {
          steps {
            sh 'echo "Hello world"'
          }
        }

        stage('build app') {
          steps {
            sh '''#! /bin/bash
gradle clean shadowjar -p app'''
          }
        }

      }
    }

  }
}