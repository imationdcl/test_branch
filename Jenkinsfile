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
		sh 'git fetch'
		sh 'git checkout ${BRANCH_NAME}'
            }
        }
        
    }
}
