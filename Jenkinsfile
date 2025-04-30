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
               withCredentials([usernamePassword(credentialsId: 'f70e73ef-7623-455b-a5ab-a637fbdf8701', usernameVariable: 'GIT_USERNAME', passwordVariable: 'GIT_PASSWORD')]) {
    sh 'git clone https://${GIT_USERNAME}:${GIT_PASSWORD}@github.com/poky789456/projet-dev01.git'
}

            }
        }
    }
}
