pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building docker image'
        sh 'bat \'docker build -t data-eng:latest .\''
      }
    }

    stage('Run') {
      steps {
        echo 'Run the app'
        sh 'bat \'docker run --name PROJET -d -p 5000:5000 data-eng\''
      }
    }

    stage('Testing') {
      steps {
        echo 'Testing...'
        sh 'bat \'docker run --name PROJET -d -p 5000:5000 data-eng\''
      }
    }

    stage('Stop the containers') {
      steps {
        echo 'Stopping containers'
        sh 'bat \'docker pause PROJET\''
        sh 'bat \'docker container rm --force PROJET\''
        sh 'bat \'docker image rm --force data-eng\''
      }
    }

  }
}