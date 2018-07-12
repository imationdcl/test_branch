pipeline {
    agent any 

    stages {
        stage('Prepare') {
            steps {
                sh 'echo "preparacion del ambiente y limpiar ambiente de trabajo"'
            }
        }
        stage('Test'){
            steps {
                sh 'echo "corriendo los test unitarios"'
	    }
        }
        stage('Deploy') {
            steps {
		sh 'cd /var/www/html/prueba'
		sh 'rm -rf *'
		sh 'git clone ${GIT_URL}'
		sh 'git fetch'
		sh 'git checkout ${BRANCH_NAME}'
		sh 'git pull origin ${BRANCH_NAME}'
            }
        }
	stage('SonarQube analysis') {
	    steps {
		// requires SonarQube Scanner 2.8+
		//def scannerHome = tool 'SonarQube Scanner 2.8';
		withSonarQubeEnv('SonarQube Server') {
			sh "/home/anibal/Descargas/sonar-scanner-3.2.0.1227-linux/bin/sonar-scanner -Dsonar.projectKey=test_branch   -Dsonar.sources=.  -Dsonar.host.url=http://localhost:9000 "
		}
	    }
	}
        
    }
}
