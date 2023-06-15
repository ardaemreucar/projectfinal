pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
            echo " githubtan proje ındırılıyor"
                sh "https://github.com/ardaemreucar/projectfinal.git"
            echo "ındırılen projenın workspacede dızın altına gırılıyor"
                sh "cd projectfinal/infrastructure"
            }
        }
        stage('Deploy') {
            steps {
            echo "cli cloudformatıon oluşturma komutu ıle gıthubtan ındırmıs oldugumuz template ıle stack oluturuluyor"
                 sh "aws cloudformation create-stack --stack-name denemestack --template-body file:///var/lib/jenkins/workspace/prjtask3/projectfinal/infrastructure/cfn-template.yaml --parameters ParameterKey=KeyPairName,ParameterValue=keypair --capabilities CAPABILITY_IAM"
            }
        }
    }
}
