pipeline {
  agent any
  stages {
    stage('setup') {
      steps {
        sh 'npm ci'
      }
    }

    stage('check:lint') {
      parallel {
        stage('check:lint') {
          steps {
            sh 'nx lint'
          }
        }

        stage('npm audit') {
          steps {
            sh 'npm audit'
          }
        }

      }
    }

    stage('test') {
      steps {
        sh 'nx test'
      }
    }

    stage('build') {
      steps {
        sh 'nx build'
      }
    }

  }
}