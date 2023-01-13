pipeline{
    agent any
    tools {
        terraform 'terraform'
    }
    stages{

          stage('terraform init'){
            steps{
                sh 'terraform init'
            }
        }
        
          stage('AWS credentials'){
            steps{
                withCredentials([[
                    $class: 'AmazonWebServicesCredentialsBinding',
                    credentialsId: "aws-jenkinse",
                    accessKeyVariable: 'AWS_ACCESS_KEY_ID',
                    secretKeyVariable: 'AWS_SECRET_ACCESS_KEY'
                ]]) {
    // AWS Code
}
            }
        }
        
        stage('terraform init'){
            steps{
                sh 'terraform init'
            }
        }
    }
}