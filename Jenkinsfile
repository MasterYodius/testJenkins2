pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building docker image'
        bat 'docker build -t data-eng:latest .'
      }
    }

    stage('Run') {
      steps {
        echo 'Run the app'
        bat 'docker run --name PROJET -d -p 5000:5000 data-eng'
      }
    }

    stage('Testing') {
      steps {
        echo 'Testing...'
        bat 'docker run --name PROJET -d -p 5000:5000 data-eng'
      }
    }

    stage('Stop the containers') {
      steps {
        echo 'Stopping containers'
        bat 'docker pause PROJET'
        bat 'docker container rm --force PROJET'
        bat 'docker image rm --force data-eng'
      }
    }

  }
}