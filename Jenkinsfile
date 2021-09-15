pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
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
