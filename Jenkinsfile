pipeline {
  agent any
  stages {
    stage('clone') {
      steps {
        git(url: 'https://github.com/narendrasingamaneni91/Narendraapplication.git', branch: 'Master')
      }
    }

    stage('compile') {
      parallel {
        stage('compile') {
          steps {
            bat 'mvn compile'
          }
        }

        stage('test') {
          steps {
            bat 'mvn test'
          }
        }

        stage('install') {
          steps {
            bat 'mvn install'
          }
        }

      }
    }

    stage('sonarqube') {
      steps {
        bat 'REM mvn sonar::sonar'
      }
    }

  }
}