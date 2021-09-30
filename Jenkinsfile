pipeline{
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/donv1789/todolist-simple.git'
            }
        }
        stage('Clone') {
            steps {
                withDockerRegistry(credentialsId: '123', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t donv1789/todolist:v10'
                    sh 'docker push -t donv1789/todolist:v10'
                }
            }
        }
    }
}