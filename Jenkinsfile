pipeline {

  agent any
   
   stage('git checkout'){
      try {
      git credentialsId: 'AWS-SCRET', url: 'https://github.com/dipakparmar13/jenkins.git'
      } catch(err) {
         sh "echo error in checkout"
      }
   }
   stage('artifacts to s3') {
      try {
      
          withCredentials([<object of type com.cloudbees.jenkins.plugins.awscredentials.AmazonWebServicesCredentialsBinding>]) {
           sh 'aws s3 ls'  
           sh 'aws s3 cp index.html s3://productionbranch'
         }
      } catch(err) {
         sh "echo error in sending artifacts to s3"
      }
   }
}

   