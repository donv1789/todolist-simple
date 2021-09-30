// pipeline{
    // agent any
    // stages {
    //     stage('Clone') {
    //         steps {
    //             git 'https://github.com/donv1789/todolist-simple.git'
    //         }
    //     }
        
    // }('Slave2')
    node{
    stage('Build') {
        sh '''echo build steps'''
    }
    stage('Test') {
        sh '''echo test steps'''
    }
}
// }