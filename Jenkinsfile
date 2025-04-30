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
                git branch: 'master', credentialsId: 'f70e73ef-7623-455b-a5ab-a637fbdf8701', url: 'https://github.com/poky789456/projet-dev01.git'
                   }

            }
        
                stage('Build image docker') {
            steps {
              script {
                  sh 'docker build -t myimage_nginx .'
                  sh 'docker tag myimage_nginx bradley:myimage_nginx'
              }

            }
        }
            stage('Deploiement application') {
            steps {
              script {    
                  sh 'docker stop monapp'
                  sh 'docker rm monapp'   
                  sh 'docker run -d --name monapp --hostname monapp -p 8099:80 myimage_nginx'
                  sh 'docker exec monapp "ifconfig"'
              }

            }
        }
    }
}
