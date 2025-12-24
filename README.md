# Introduction 
# Azure DevOps Real-World CI/CD Project

## Objective
To design and implement CI/CD pipelines in Azure DevOps using YAML, following real industry practices.

## Day 1 Progress
- Azure DevOps project created
- Git repository initialized
- Application structure defined
- Initial commit completed

## Tech Stack
- Azure DevOps
- Git
- HTML
- Bash

## Next Steps
- Implement CI pipeline using YAML
🚀 Azure DevOps CI/CD – Real-World Pipeline Project
📌 Project Overview

This project demonstrates a real-world, enterprise-grade CI/CD pipeline built using Azure DevOps YAML pipelines.
It covers the complete lifecycle from CI to CD, including security, governance, approvals, and pipeline hardening.

The focus of this project is hands-on DevOps practices, troubleshooting, and production-safe design — not just a “happy-path” demo.

🧱 Architecture Overview

Pipeline Flow:

Commit / PR
   ↓
Build Stage
   ↓
Test Stage
   ↓
Deploy to Dev (main only)
   ↓
Manual Approval
   ↓
Deploy to Prod (main only)

🛠️ Tools & Technologies

Azure DevOps

YAML Pipelines

Environments (Dev & Prod)

Variable Groups (Secrets)

Branch Policies

Git

Self-Hosted Linux Agent

GitHub (final repository after migration)

⚙️ Key Features Implemented
✅ Continuous Integration (CI)

YAML-based pipeline

Build and Test stages

Structured logs with timestamps and context

Runs on all branches and PRs

✅ Continuous Deployment (CD)

Deployment stages using deployment jobs

Separate Dev and Prod environments

Manual approval gate before Prod deployment

✅ Security & Secrets

Secrets managed using Azure DevOps Variable Groups

Secret masking verified in pipeline logs

No secrets hard-coded in YAML

✅ Governance & Quality Gates

Branch policies on main (Lab exercise)

Pull Request build validation

PR blocking on pipeline failure

Clean rollback of policies after lab completion

✅ Pipeline Hardening (Enterprise Design)

Deployments restricted to main branch only

No deployments triggered from PRs or feature branches

Conditional stage execution using pipeline expressions

Cost-safe and production-safe pipeline behavior

🔐 Example: Deployment Hardening Logic
condition: |
  and(
    succeeded(),
    eq(variables['Build.SourceBranch'], 'refs/heads/main')
  )


This ensures:

CI runs everywhere

CD runs only from main

Production is protected by design

🧪 Labs Performed (Hands-On)

CI pipeline creation & troubleshooting

Self-hosted agent setup

Multi-stage YAML pipelines

Environments & approvals

Secret masking verification

Intentional pipeline failures & RCA

Branch policy enforcement & rollback

Deployment hardening with conditions

Azure DevOps → GitHub migration

📂 Repository Structure
.
├── .azure-pipelines/
│   └── ci.yml
├── README.md
└── (application / placeholder files)

🧠 Interview Talking Points

You can confidently explain:

Difference between job and deployment job

Why approvals alone are not enough for Prod safety

How branch policies protect main

How pipeline conditions prevent risky deployments

How secrets are securely handled

How CI/CD failures are diagnosed and fixed

🎯 Why This Project Matters

This project was built to:

Simulate real enterprise CI/CD workflows

Practice failure handling and governance

Build interview-ready DevOps confidence

Avoid tutorial-only or copy-paste projects

🔗 Repository Status

✅ Azure DevOps project archived after migration

✅ GitHub is the primary source of truth

✅ Full commit history preserved

📌 Next Steps (Optional Enhancements)

GitHub Actions implementation (CI/CD comparison)

Dockerization of sample app

Kubernetes deployment (Minikube / Kind)

Terraform-based infrastructure pipeline

👤 Author

Ashish Mondal
DevOps | Cloud | CI/CD
Hands-on learning with real-world pipelines
