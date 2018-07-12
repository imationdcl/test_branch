pipeline {
    agent any 

    stages {
        stage('Prepare') {
            steps {
                sh 'echo "preparacion del ambiente"'
            }
        }
        stage('PHP Syntax check') { steps { sh 'echo "checkeo de sintaxis"' } }
        stage('Test'){
            steps {
                sh 'echo "corriendo los test unitarios"'
	    }
        }
        stage('Checkstyle') {
            steps {
		sh 'echo "Mirando estilo de codigo"'
            }
        }
        stage('Lines of Code') { 
	    steps {
		 sh 'echo "lineas de codigo"' 
	    }
	}
        
        stage('Mess detection') {
            steps {
                sh 'echo "deteccion de codigo basura"'
            }
        }
        stage('Software metrics') { steps { sh 'echo "generacion de metricas"' } }
        stage('Generate documentation') { steps { sh 'echo "documentacion"' } }
        
    }
}
