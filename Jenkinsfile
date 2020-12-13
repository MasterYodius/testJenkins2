pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building docker image'
        sh 'sh \'docker build -t data-eng:latest .\''
      }
    }

    stage('Run') {
      steps {
        echo 'Run the app'
        sh 'sh \'docker run --name PROJET -d -p 5000:5000 data-eng\''
      }
    }

    stage('Testing') {
      steps {
        echo 'Testing...'
        sh 'sh \'docker run --name PROJET -d -p 5000:5000 data-eng\''
      }
    }

    stage('Stop the containers') {
      steps {
        echo 'Stopping containers'
        sh 'sh \'docker pause PROJET\''
        sh 'sh \'docker container rm --force PROJET\''
        sh 'sh \'docker image rm --force data-eng\''
      }
    }

  }
}