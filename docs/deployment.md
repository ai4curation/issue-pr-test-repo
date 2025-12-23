# Deployment Guide

## Prerequisites

- Docker installed
- Access to production environment
- Valid credentials

## Deployment Steps

1. **Build the application**
   ```bash
   docker build -t test-app:latest .
   ```

2. **Push to registry**
   ```bash
   docker push registry.example.com/test-app:latest
   ```

3. **Deploy to production**
   ```bash
   kubectl apply -f k8s/production.yaml
   ```

## Configuration

Production configuration is stored in `config/production.yaml`.

Key differences from development:
- SSL enabled
- Rate limiting active
- Increased connection pool
- File-based logging

## Rollback

To rollback to a previous version:
```bash
kubectl rollout undo deployment/test-app
```

## Monitoring

Check deployment status:
```bash
kubectl get pods -l app=test-app
```
