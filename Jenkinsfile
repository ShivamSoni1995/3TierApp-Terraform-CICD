pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'ap-south-1'
        BRANCH = "main"
        GIT_REPO = "https://github.com/ShivamSoni1995/3TierApp-Terraform-CICD.git"
        AWS_ACCESS_KEY_ID = credentials('my-aws-credentials-id') // Replace with your credential ID
        AWS_SECRET_ACCESS_KEY = credentials('my-aws-credentials-id') // Replace with your credential ID
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: "${BRANCH}", credentialsId: 'github-creds', url: "${GIT_REPO}"
            }
        }
        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Terraform Validate') {
            steps {
                sh 'terraform validate'
            }
        }
        stage('Terraform Plan') {
            steps {
                sh 'terraform plan -out=tfplan'
            }
        }
        stage('Approval') {
            steps {
                input message: 'Approve to apply Terraform changes?'
            }
        }
        stage('Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve tfplan'
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}