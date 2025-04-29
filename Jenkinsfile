pipeline {
  agent any
  stages {
    stage('Parallel execution') {
      parallel {
        stage('say hello') {
          steps {
            sh 'echo "hello world"'
          }
        }

        stage('buid-app') {
          agent {
            docker {
              image 'gradle:6-jdk11'
            }

          }
          steps {
            sh 'ci/build-app.sh'
          }
        }

      }
    }

  }
}