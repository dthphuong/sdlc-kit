---
description: Deploy application to local, Kubernetes, or server with automatic domain mapping
agent: devops
model: zai/glm-4.7
---

Deploy: $ARGUMENTS

## Command Usage

```
/deploy [app_name] to [environment] [options]
```

**Environments:**
- `local` - Docker Compose + Traefik (e.g., `myapp.local`)
- `k8s` - Kubernetes + Ingress (e.g., `myapp.k8s.local`)
- `server` - Traditional server (e.g., `myapp.example.com`)

**Options:**
- `with domain [domain]` - Custom domain name
- `--ssl` - Enable SSL/TLS
- `--no-ssl` - Disable SSL/TLS

**Examples:**
- `/deploy myapp to local` → http://myapp.local
- `/deploy myapp to k8s` → https://myapp.k8s.local
- `/deploy myapp to server with domain api.example.com` → https://api.example.com

---

## File Output

Save deployment report to:
- **Location:** `./report/` folder
- **Filename:** `DEPLOY_YYYYmmdd_HHMMSS.md`

---

## Deployment Process

### Phase 1: Environment Detection

1. Detect target environment (local, k8s, server)
2. Generate domain name based on app name and environment
3. Check prerequisites for the environment

### Phase 2: Configuration Generation

Based on environment, generate appropriate files:

#### Local Deployment
```
./deploy/
├── docker-compose.traefik.yml    # Traefik reverse proxy
├── docker-compose.local.yml      # Application config
└── setup-local-dns.sh            # dnsmasq setup script
```

#### Kubernetes Deployment
```
./k8s/
├── namespace.yaml
├── deployment.yaml
├── service.yaml
├── ingress.yaml
├── configmap.yaml
└── secrets.yaml
```

#### Server Deployment
```
./terraform/
├── main.tf
├── variables.tf
└── outputs.tf

./ansible/
├── deploy.yml
├── inventory
└── templates/
```

### Phase 3: Deployment Execution

#### Local Environment
```bash
# 1. Create Traefik network (one-time)
docker network create traefik-network

# 2. Start Traefik (one-time)
docker-compose -f deploy/docker-compose.traefik.yml up -d

# 3. Deploy application
docker-compose -f deploy/docker-compose.local.yml up -d

# 4. Verify
curl http://myapp.local/health
```

#### Kubernetes Environment
```bash
# 1. Create namespace
kubectl apply -f k8s/namespace.yaml

# 2. Deploy application
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl apply -f k8s/ingress.yaml

# 3. Verify
kubectl rollout status deployment/myapp -n myapp
curl https://myapp.k8s.local/health
```

#### Server Environment
```bash
# 1. Provision infrastructure
cd terraform && terraform apply

# 2. Configure and deploy
cd ../ansible && ansible-playbook deploy.yml

# 3. Verify
curl https://myapp.example.com/health
```

### Phase 4: Verification

- [ ] Health check endpoint responds
- [ ] Domain resolves correctly
- [ ] SSL certificate valid (if enabled)
- [ ] Application logs show no errors
- [ ] Performance metrics within bounds

---

## Deployment Checklist

### Pre-Deployment
- [ ] Application builds successfully
- [ ] Tests pass
- [ ] Environment variables documented
- [ ] Secrets configured
- [ ] Domain name available

### During Deployment
- [ ] Deploy to target environment
- [ ] Configure domain routing
- [ ] Set up SSL/TLS (if applicable)
- [ ] Verify health checks
- [ ] Monitor deployment logs

### Post-Deployment
- [ ] Smoke tests pass
- [ ] Domain accessible
- [ ] SSL working (if applicable)
- [ ] Monitoring alerts configured
- [ ] Documentation updated

---

## Domain Mapping Reference

| Environment | Domain Format | Example |
|------------|---------------|---------|
| Local | `{app}.local` | `myapp.local` |
| K8s | `{app}.k8s.local` | `myapp.k8s.local` |
| Server | `{app}.{domain}` | `myapp.example.com` |

---

## Rollback Procedure

### Local
```bash
docker-compose -f deploy/docker-compose.local.yml down
docker-compose -f deploy/docker-compose.local.yml up -d --build
```

### Kubernetes
```bash
kubectl rollout undo deployment/myapp -n myapp
```

### Server
```bash
cd ansible && ansible-playbook rollback.yml
```

---

## Output Report Format

```markdown
# 🚀 Deployment Report

## Summary
**Application:** [app_name]
**Environment:** [environment]
**Domain:** [domain]
**URL:** [url]
**Status:** ✅ Success | ❌ Failed

## Deployment Steps Completed
- [x] Environment configured
- [x] Domain mapped
- [x] Application deployed
- [x] Health checks passing

## Access Information
- **URL:** [url]
- **Dashboard:** [dashboard_url]
- **Health Check:** [health_url]

## Files Created
- [list of files created]

## Next Steps
1. Verify application functionality
2. Run integration tests
3. Monitor for errors
4. Update team documentation
```
