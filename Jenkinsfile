pipeline {
  agent any
  tools {
    maven '3.9.5'
  }
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/lukasowy/spring-boot-testing-pyramid', branch: 'master')
      }
    }

    stage('Parallel') {
      parallel {
        stage('Log') {
          steps {
            sh 'ls -la'
          }
        }

        stage('Tests') {
          steps {
            sh 'mvn test'
          }
        }

        stage('Maven version') {
          steps {
            sh 'mvn --version'
          }
        }

      }
    }

  }
}