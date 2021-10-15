pipeline{

    agent {label 'master'}

    environment {
        DOCKERHUB_CREDENTIALS=credentials('docker-hub')
    }

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/donv1789/todolist-simple.git'
            }
        }
        

        stage('Build') {
            steps {
                sh 'docker build -t donv1789/todolist1:latest .'
            }
        }

         stage('Login'){

            steps {                  
                    sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                }

            }

        stage('Push'){

            steps {                  
                    sh 'docker push donv1789/todolist1:latest'
                    sh 'docker logout'
                    echo 'logout docker'
                }

            }
            stage('update-content'){
            steps {    
                    sh 'docker-compose down'
                    sh 'docker-compose build --no-cache'
                    sh 'docker-compose up -d'               
                }
            }
    }
    // post {
    //     always {
    //         sh 'docker logout'
    //     }
    // }
    
}
 