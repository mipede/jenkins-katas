pipeline {
  agent {
    docker {
      image 'gradle:6-jdk11'
    }

  }
  stages {
       stage('clone down') {
          steps {
            stash excludes: '.git', name: 'code'
          }
        }
    stage('Say Hello') {
      parallel {
        stage('Parallel execution') {
          steps {
            sh 'echo "Hello world"'
          }
        }

        stage('build app') {
          steps {
            unstash 'code'
            skipDefaultCheckout(true)
            sh '''#! /bin/bash
gradle clean shadowjar -p app'''
            archiveArtifacts 'app/build/libs/'
            sh 'ls'
            deleteDir()
            sh 'ls'
          }
        }

      }
    }
      }
  }
}