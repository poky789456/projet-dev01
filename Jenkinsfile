pipeline {
    agent any
    stages {
        stage('Supprimer le workspace') {
            steps {
                deleteDir()
            }
        }
        stage('Checkout SCM') {
            steps {
                sh 'git clone https://github.com/poky789456/projet-dev01.git'
            }
        }
    }
}
