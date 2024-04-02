pipeline {
    agent any
	
    stages {
		stage('pre cleanup') {
			steps {
				sh 'docker compose down'
			}
		}
		stage('git scm update') {
			steps {
				git url: 'https://github.com/jjh920/fastapi-app.git', branch: 'main'
			}
		}
        stage('docker build & deploy') {
            steps {
				sh '''
                docker compose up --build -d
				'''
            }
        }
    }
}
