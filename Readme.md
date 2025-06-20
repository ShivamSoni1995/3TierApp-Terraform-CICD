

🛠️ Setup Instructions
✅ Prerequisites

    AWS CLI configured (aws configure)

    Terraform installed (v1.3+)

    Jenkins running (can be local or on EC2)

    Git & GitHub repo for storing code

🚀 Deploy Infrastructure
```
# Initialize Terraform
terraform init

# Format & Validate
terraform fmt
terraform validate

# Preview changes
terraform plan -out=tfplan

# Apply the infrastructure
terraform apply tfplan
```

🔄 CI/CD Pipeline with Jenkins
Jenkinsfile Workflow:

    Clone Repo – Pulls latest Terraform code from GitHub.

    Terraform Init – Initializes backend.

    Terraform Validate – Checks syntax and config.

    Terraform Plan – Shows proposed changes.

    Terraform Apply – Applies infrastructure (manual approval optional).

📤 Outputs

Once deployed, Terraform provides outputs such as:

    Public IP of Web Tier

    RDS Endpoint

    VPC ID

🔒 Security Best Practices

    Resources use least privilege IAM roles.

    All infrastructure is deployed in isolated VPCs.

    RDS instance is not exposed to the internet.

    Use of tags for cost management and resource tracking.

🙌 Contributing

Feel free to fork, improve and submit a pull request. Suggestions for improvement or optimization are welcome.
📄 License

This project is licensed under the MIT License.





