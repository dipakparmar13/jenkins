pipeline {
    agent any

     stages {
        stage('Hello') {
            steps {
               sh 'pwd'
               sh 'ls'
                
        }
    }
    node ('main'){
    stage 'Checkout'
    checkout scm
    stage "Build Pex"
    sh('dipak.sh')
}
}
}
