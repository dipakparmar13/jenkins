pipeline {

  agent any

  stages {
     try {
          withCredentials([<object of type com.cloudbees.jenkins.plugins.awscredentials.AmazonWebServicesCredentialsBinding>]) {
           sh 'aws s3 ls'  
           sh 'aws s3 cp index.html s3://productionbranch'
         }
     }
   