# 🚀 AWS EKS DevOps Portfolio

Production-ready AWS EKS DevOps portfolio project with Terraform IaC, CI/CD pipelines, Kubernetes blue/green deployments, and full observability stack.

## ⚡ Quick Start - Get Complete Project in 1 Command

Run this single command to generate ALL 50+ project files instantly:

```bash
curl -sSL https://gist.githubusercontent.com/vkoneru7-gif/599b245b6fb5e7f16f2b56e2fb2f73e0/raw/generate-aws-eks-devops-portfolio.sh | bash
```

Or clone and run locally:

```bash
git clone https://github.com/vkoneru7-gif/aws-eks-devops-portfolio.git
cd aws-eks-devops-portfolio
curl -O https://gist.githubusercontent.com/vkoneru7-gif/599b245b6fb5e7f16f2b56e2fb2f73e0/raw/generate-aws-eks-devops-portfolio.sh
chmod +x generate-aws-eks-devops-portfolio.sh
./generate-aws-eks-devops-portfolio.sh
```

## 📦 What's Included

This project demonstrates enterprise-level DevOps practices with:

### Infrastructure (Terraform)
✅ Multi-AZ VPC with public/private subnets  
✅ EKS cluster with managed node groups  
✅ RDS PostgreSQL with encryption  
✅ IAM roles with IRSA (no long-lived keys)  
✅ Security groups (least-privilege)  
✅ VPC endpoints for cost optimization  
✅ Separate dev/prod configurations  

### Application
✅ FastAPI backend with /tasks CRUD API  
✅ React frontend SPA  
✅ Dockerfiles for both services  
✅ Prometheus metrics instrumentation  

### CI/CD (GitHub Actions + OIDC)
✅ Build and test workflow  
✅ Security scanning (Trivy)  
✅ Automated EKS deployment  
✅ OIDC-based AWS authentication  
✅ Multi-environment support  

### Kubernetes
✅ Blue/Green deployment strategy  
✅ Helm charts with values for dev/prod  
✅ Ingress with AWS Load Balancer Controller  
✅ ConfigMaps and Secrets  
✅ Resource limits configured  

### Observability
✅ Prometheus + Grafana via Helm  
✅ 3 alert rules (error rate, latency, pod restarts)  
✅ 2 Grafana dashboards (app + cluster)  
✅ CloudWatch integration  

## 🏗️ Project Structure

```
aws-eks-devops-portfolio/
├── .github/workflows/          # CI/CD Pipelines
│   ├── build-and-test.yml
│   ├── security-scan.yml
│   └── deploy.yml
├── app/
│   ├── api/                    # FastAPI Backend
│   └── frontend/               # React Frontend
├── infra/terraform/            # Infrastructure as Code
│   ├── main.tf
│   ├── vpc.tf
│   ├── eks.tf
│   ├── rds.tf
│   └── envs/dev/ and envs/prod/
├── k8s/helm/taskhub/           # Kubernetes Helm Chart
│   ├── Chart.yaml
│   ├── values.yaml
│   └── templates/
├── monitoring/
│   ├── prometheus/
│   └── grafana/
└── docs/
    ├── README.md
    ├── architecture.md
    └── runbook.md
```

## 🔧 Setup Instructions

### Prerequisites
- AWS CLI configured with appropriate credentials
- Terraform >= 1.6.0
- kubectl
- Helm 3
- Docker

### Step 1: Generate Project Files
```bash
curl -sSL https://gist.githubusercontent.com/vkoneru7-gif/599b245b6fb5e7f16f2b56e2fb2f73e0/raw/generate-aws-eks-devops-portfolio.sh | bash
```

### Step 2: Customize Placeholders
Search for `TODO` comments and replace:
- `<YOUR-AWS-ACCOUNT-ID>` → Your AWS account number
- `<YOUR-TF-STATE-BUCKET>` → S3 bucket for Terraform state
- `<YOUR-DYNAMODB-LOCK-TABLE>` → DynamoDB table for state locking
- Database credentials in `terraform.tfvars`

### Step 3: Deploy Infrastructure
```bash
cd infra/terraform/envs/dev
terraform init
terraform plan
terraform apply
```

### Step 4: Configure kubectl
```bash
aws eks update-kubeconfig --name taskhub-dev-eks --region us-east-1
```

### Step 5: Deploy Application
```bash
cd ../../../../k8s/helm
helm install taskhub ./taskhub -f taskhub/values.yaml
```

## 💼 For Interviews

### Key Talking Points
1. **Multi-environment IaC strategy** - Separate dev/prod with Terraform modules
2. **Modern CI/CD with zero long-lived credentials** - GitHub Actions OIDC to AWS
3. **Production-grade Kubernetes** - Blue/green deployments, resource limits
4. **Full observability stack** - Prometheus metrics, Grafana dashboards, alert rules
5. **Security-first approach** - Private subnets, encrypted RDS, security scanning

### Demo Flow
1. Show GitHub repo structure
2. Walk through Terraform architecture (VPC → EKS → RDS)
3. Explain CI/CD pipeline (build → scan → deploy)
4. Demonstrate blue/green deployment in Helm
5. Show Grafana dashboards and Prometheus alerts

## 📚 Documentation

- **[Architecture Guide](docs/architecture.md)** - System architecture and component descriptions
- **[Runbook](docs/runbook.md)** - Deployment steps, rollback procedures, troubleshooting
- **[Complete Project Generator](https://gist.github.com/vkoneru7-gif/599b245b6fb5e7f16f2b56e2fb2f73e0)** - Script to create all files

## 🎯 Why This Project Stands Out

This project demonstrates DevOps Lead-level expertise:
- Real production patterns (not toy examples)
- Security-first design (OIDC, private subnets, IRSA)
- Complete automation (Infrastructure + CI/CD + Monitoring)
- Enterprise observability (metrics, logs, alerts, dashboards)
- Proper documentation (architecture, runbooks, diagrams)

## 📞 Contact

Built as a portfolio project showcasing production-ready DevOps practices.

**Repository:** https://github.com/vkoneru7-gif/aws-eks-devops-portfolio  
**Project Generator:** https://gist.github.com/vkoneru7-gif/599b245b6fb5e7f16f2b56e2fb2f73e0
