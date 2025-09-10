**#Project Overview**

This is a simple React web application deployed to AWS S3 and served via CloudFront using a CI/CD pipeline powered by GitHub Actions.

**#Features**

Fully automated build & deploy on main branch push
Hosted on AWS S3 + CloudFront (static website)
Easy rollback by reverting commits
Beginner-friendly CI/CD setup

**#Prerequisites**

Before running or deploying this project, make sure you have:
Node.js and npm installed on your system
Git installed and configured
An AWS account with:
S3 bucket for website hosting
CloudFront distribution
IAM user with AmazonS3FullAccess and CloudFrontFullAccess

**#Project Setup (Local)**

Clone the repository:
git clone https://github.com/hesam009/react-app.git
cd react-app

**#CI/CD Pipeline Setup**

GitHub Actions Workflow is located in:
.github/workflows/deploy.yml


**Add GitHub Secrets for AWS access:**

AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY

Go to GitHub → Repository → Settings → Secrets → Actions → New repository secret

**Push changes to main branch:**

git add .
git commit -m "your commit message"
git push origin main


**GitHub Actions will automatically:**

Build the app
Deploy to S3
Invalidate CloudFront cache

**CloudFront & S3 Settings**

S3 bucket: Static website hosting enabled
CloudFront: Origin points to S3 website endpoint, cache invalidation enabled in GitHub Actions

**Rollback**

If deployment breaks:

git revert <commit-id>
git push origin main
GitHub Actions redeploys the previous version automatically
