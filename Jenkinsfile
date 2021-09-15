pipeline {
    agent any
    environment {
        aws-credentials = credentials('aws-credentials')
    }
    stages {
        stage('Init-plan') {
            steps {
                sh 'terraform init'
                sh 'terraform plan -out=tfplan'
             }      
        }
        stage('Apply') {
            steps {
                sh 'terraform apply tfplan -auto-approve'
                }
            }
        stage('Destroy') {
            steps {
                echo 'terraform destroy -auto-approve'
            }
        }
    }
}
