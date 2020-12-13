pipeline{
	agent any
	stages{
		stage('Build'){
			steps{
				echo 'Building docker image'
				bat 'docker build -t data-eng:latest .'
			}
		}
		stage('Run'){		
			steps{
				echo ('Run the app')
				bat 'docker run --name PROJET -d -p 5000:5000 data-eng'
			}
		}
		stage('Testing'){
			steps{
				bat 'C:/Users/alex-/AppData/Local/Programs/Python/Python37/python.exe tests.py'
			}
		}
		stage('Stop Containers'){
			
			steps{
				bat 'docker pause PROJET'
				bat 'docker container rm --force PROJET'
				bat 'docker image rm --force data-eng'
			}
			
		}
	}
}
