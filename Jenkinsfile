pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Clone the repository from GitHub
                git 'https://github.com/venkat1346/terraform22.git'
            }
        }
        
        stage('Terraform Init') {
            steps {
                // Install and initialize Terraform
                sh 'curl -LO https://releases.hashicorp.com/terraform/0.14.7/terraform_0.14.7_linux_amd64.zip'
                sh 'unzip terraform_0.14.7_linux_amd64.zip'
                sh 'chmod +x terraform'
                sh './terraform init'
            }
        }
        
        stage('Terraform Plan') {
            steps {
                // Run Terraform plan
                sh './terraform plan'
            }
        }
        
        stage('Terraform Apply') {
            steps {
                // Apply Terraform changes
                sh './terraform apply --auto-approve'
            }
        }
        
        stage('Terraform Destroy') {
            steps {
                // Destroy Terraform resources
                sh './terraform destroy --auto-approve'
            }
        }
    }
}
