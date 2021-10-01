pipeline{

    agent any 

    stages {

        // stage('Git-Clone'){

        //     steps {

        //         git 'https://github.com/donv1789/todolist-simple.git'

        //     }

        // }

         stage('Hub-push'){

            steps {

                    withDockerRegistry(credentialsId: 'docker-agent-userwithpass2', url: 'https://index.docker.io/v1/') {

}

                    sh 'docker login -u donv1789 -p Do@178199'

                    sh 'docker build -t donv1789/todolist:v10 .'

                    sh 'docker push donv1789/todolist:v10'

                }

            }

        }

    }