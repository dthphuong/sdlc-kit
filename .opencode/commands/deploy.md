---
description: Set up deployment configuration and CI/CD pipeline
agent: devops
model: zai/glm-4.7
---

Set up deployment and CI/CD for: $ARGUMENTS

## Deployment Requirements

### 1. Analyze Project
- [ ] Identify project type (Node.js, Python, etc.)
- [ ] Determine dependencies
- [ ] Identify build requirements
- [ ] Check for environment variables
- [ ] Assess resource needs

### 2. Create Deployment Files

#### Dockerfile
```dockerfile
# Create optimized multi-stage Dockerfile
# Include:
# - Proper base image
# - Dependency installation
# - Build steps
# - Production optimization
# - Security best practices
# - Health checks
```

#### docker-compose.yml (if applicable)
```yaml
# Define services:
# - Application container
# - Database
# - Redis/cache
# - Networks
# - Volumes
```

### 3. CI/CD Pipeline

#### GitHub Actions
Create `.github/workflows/ci.yml`:
- [ ] Lint and test on PR
- [ ] Build on merge
- [ ] Deploy to staging
- [ ] Deploy to production
- [ ] Run security scans

### 4. Environment Configuration
- [ ] Create .env.example
- [ ] Document required variables
- [ ] Set up secrets management
- [ ] Configure different environments

### 5. Kubernetes (if needed)
- [ ] Deployment manifest
- [ ] Service definition
- [ ] ConfigMaps
- [ ] Secrets
- [ ] Ingress configuration

### 6. Monitoring Setup
- [ ] Health check endpoints
- [ ] Logging configuration
- [ ] Error tracking
- [ ] Performance monitoring

## Output Structure

```
project/
├── Dockerfile
├── docker-compose.yml
├── .dockerignore
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── deploy.yml
├── k8s/ (if Kubernetes)
│   ├── deployment.yaml
│   ├── service.yaml
│   └── ingress.yaml
├── .env.example
└── DEPLOYMENT.md
```

## Deployment Documentation

Create DEPLOYMENT.md with:
- [ ] Prerequisites
- [ ] Environment setup
- [ ] Build instructions
- [ ] Deployment steps
- [ ] Rollback procedures
- [ ] Troubleshooting guide

Ensure:
- Security best practices
- Minimal attack surface
- Proper resource limits
- Health monitoring
- Easy rollback capability
