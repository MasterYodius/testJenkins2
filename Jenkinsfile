pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building docker image'
        bat 'bat \'docker build -t data-eng:latest .\''
      }
    }

    stage('Run') {
      steps {
        echo 'Run the app'
        bat 'bat \'docker run --name PROJET -d -p 5000:5000 data-eng\''
      }
    }

    stage('Testing') {
      steps {
        echo 'Testing...'
        bat 'bat \'docker run --name PROJET -d -p 5000:5000 data-eng\''
      }
    }

    stage('Stop the containers') {
      steps {
        echo 'Stopping containers'
        bat 'bat \'docker pause PROJET\''
        bat 'bat \'docker container rm --force PROJET\''
        bat 'bat \'docker image rm --force data-eng\''
      }
    }

  }
}