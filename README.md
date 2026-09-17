# EKS Dashboard

A Kubernetes dashboard deployed on AWS EKS to monitor and manage workloads through a web interface.

## Phase 1 — EKS Dashboard Deployment

### Architecture

```text
Internet
   |
   v
AWS Load Balancer
   |
   v
Frontend (Nginx)
   |
   +---- /api ----> Backend (FastAPI)
   |
   +---- /auth ---> Backend
   |
   +---- /ws -----> Backend WebSocket
                       |
                       v
                  Kubernetes API
                       |
             +---------+---------+
             |         |         |
            Pods   Deployments  Services
                       |
                  Metrics Server

