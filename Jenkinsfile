pipeline {

  agent any
   
   stage('git checkout'){
      try {
     git branch: 'main', url: 'https://github.com/dipakparmar13/jenkins.git'
      } catch(err) {
         sh "echo error in checkout"
      }
   }
   stage('artifacts to s3') {
      try {
      
           withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'AWS-SCRET', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
           sh "aws s3 ls"
           sh 'aws s3 ls'  
           sh 'aws s3 cp index.html s3://productionbranch'
         }
      } catch(err) {
         sh "echo error in sending artifacts to s3"
      }
   }
}

   