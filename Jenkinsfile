pipeline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/lukasowy/spring-boot-testing-pyramid', branch: 'master')
      }
    }

    stage('Log') {
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

        stage('Maven') {
          steps {
            sh 'mvn --version'
          }
        }

      }
    }

  }
}