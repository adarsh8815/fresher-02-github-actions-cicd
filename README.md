# Project 2: GitHub Actions — CI/CD Pipeline

## What You Will Learn
- What GitHub Actions is and how it works
- Writing YAML pipeline configuration
- Automated testing on every push
- Multi-job pipeline with dependencies
- Building Docker images in CI

## Pipeline Flow
```
Code Push (git push)
        ↓
  [Job 1] Run Tests (pytest)
        ↓ on success
  [Job 2] Build Docker Image
        ↓ on success
  [Job 3] Deployment Summary
```

## How to Set Up

### Step 1 — Clone the repo
```bash
git clone https://github.com/adarsh8815/fresher-02-github-actions-cicd
cd fresher-02-github-actions-cicd
```

### Step 2 — Activate GitHub Actions
```bash
mv ci-cd-pipelines .github
git add .
git commit -m "activate github actions"
git push
```

### Step 3 — Trigger the pipeline
```bash
echo "# trigger" >> app/app.py
git add . && git commit -m "test: trigger pipeline"
git push
# Go to GitHub → Actions tab to see it run
```

## Key GitHub Actions Concepts

| Concept | Description |
|---------|-------------|
| `on: push` | Run when code is pushed |
| `jobs` | Parallel or sequential tasks |
| `steps` | Individual commands inside a job |
| `uses` | Reference a pre-built action |
| `run` | Execute a shell command |
| `needs` | Wait for another job to complete |
| `secrets` | Store passwords/tokens securely |
| `environment` | Deployment environment gate |

## Resume Line
> "Implemented CI/CD pipeline using GitHub Actions with automated pytest testing, Docker image build, and multi-job workflow with job dependency management."
