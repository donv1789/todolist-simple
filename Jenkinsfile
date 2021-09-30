pipeline{
    // agent any
    // stages {
    //     stage('Clone') {
    //         steps {
    //             git 'https://github.com/donv1789/todolist-simple.git'
    //         }
    //     }
        
    // }
    node('Slave2'){
    stage('Build') {
        sh '''echo build steps'''
    }
    stage('Test') {
        sh '''echo test steps'''
    }
}
}