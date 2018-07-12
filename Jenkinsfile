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
        
    }
}
