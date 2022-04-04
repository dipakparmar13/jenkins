pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
       echo "iiiiiiiiiiiiiiiiii"
        git branch: "main",
          url: 'https://github.com/dipakparmar13/jenkins.git'
               echo "2222222222222222"
      }
    }

    stage('Upload to S3') {
        steps{
            script {

                dir(''){
                         echo "33333333333333"
                   withCredentials([<object of type com.cloudbees.jenkins.plugins.awscredentials.AmazonWebServicesCredentialsBinding>]) {
                    echo "44444444444444444444"
                        def identity=awsIdentity();//Log AWS credentials
                               echo "555555555555555"
                        // Upload files from working directory '' in your project workspace
                        s3Upload(bucket:"productionbranch", workingDir:'', includePathPattern:'**/*');
                        // invalidate CloudFront distribution
                        cfInvalidate(distribution:'EY8I35Z7WXLW6', paths:['/*'])
                    }

                };
            }
        }
    }

  }

}
