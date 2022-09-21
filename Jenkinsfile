pipeline {
  agent any
  stages {
    stage('Get Code') {
      steps {
        git(url: 'https://github.com/elanglet/projet-banque.git', branch: 'master')
      }
    }

    stage('Build') {
      steps {
        bat 'mvn -f banque/pom.xml install'
      }
    }

    stage('Tests') {
      parallel {
        stage('Tests') {
          steps {
            junit 'banque/*/banque-web/target/surefire-reports/*.xml'
          }
        }

        stage('Message') {
          steps {
            echo 'Bla bla bla ....'
          }
        }

      }
    }

  }
}