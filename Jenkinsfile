// pipeline{
//     agent any
//     stages {
//         stage('Clone') {
//             steps {
//                 git 'https://github.com/donv1789/todolist-simple.git'
//             }
//         }
        
//     }
// }
pipeline{

    agent any

    stages {



         stage('Hub-push'){

            steps {                  

                    withCredentials([usernamePassword(credentialsId: 'docker-hub', passwordVariable: 'password', usernameVariable: 'username')]) {



                            sh 'docker build -t donv1789/todolist:v10 .'        

                            echo '$password'

                            sh 'echo $password | docker login --username $username --password-stdin'

                            echo 'login docker'

                            sh 'docker push donv1789/todolist:v10'

                            sh 'docker logout'

                            echo 'logout docker'

                    }

               

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

    }