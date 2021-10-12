pipeline{

    agent {label 'slave1'}

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
                }

            }
    }
    post {
        always {
            sh 'docker loguot'
        }
    }

           
}
 