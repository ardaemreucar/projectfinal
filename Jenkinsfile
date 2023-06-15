pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Downloading project from GitHub"
                sh "git clone https://github.com/ardaemreucar/projectfinal.git"
                echo "Entering downloaded project directory"
                sh "cd projectfinal/infrastructure"
            }
        }

        stage('Deploy') {
            steps {
                echo "Creating CloudFormation stack using the downloaded template from GitHub"
                sh "aws cloudformation create-stack --stack-name denemestack --template-body file:///var/lib/jenkins/workspace/prjtask3/projectfinal/infrastructure/cfn-template.yaml --parameters ParameterKey=KeyPairName,ParameterValue=keypair --capabilities CAPABILITY_IAM"
            }
        }
    }
}
