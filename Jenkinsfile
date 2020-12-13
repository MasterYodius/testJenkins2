pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building docker image'
        bat 'sh \'docker build -t data-eng:latest .\''
      }
    }

    stage('Run') {
      steps {
        echo 'Run the app'
        bat 'sh \'docker run --name PROJET -d -p 5000:5000 data-eng\''
      }
    }

    stage('Testing') {
      steps {
        echo 'Testing...'
        bat 'sh \'docker run --name PROJET -d -p 5000:5000 data-eng\''
      }
    }

    stage('Stop the containers') {
      steps {
        echo 'Stopping containers'
        bat 'sh \'docker pause PROJET\''
        bat 'sh \'docker container rm --force PROJET\''
        bat 'sh \'docker image rm --force data-eng\''
      }
    }

  }
}