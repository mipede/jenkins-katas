pipeline {
  agent any
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