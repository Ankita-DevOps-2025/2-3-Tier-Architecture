# P1 / P2 / P3 ISSUE CLASSIFICATION (REAL-WORLD)
================================================

# P1 — Critical / Production Down Issues
========================================
Impact: Application down, major customer impact, financial loss, SLA breach.

Application / API
- API returning 500 errors
- Application down / not reachable
- High latency causing outage
- Authentication not working
- Unhandled exceptions crashing service

Infrastructure
- Server/Node down
- CPU/Memory 100% → OOMKilled
- Disk full → service crashed
- Kernel panic
- ASG failed to scale

Networking
- Firewall/SG blocking production traffic
- DNS not resolving domain
- SSL certificate expired → app unavailable
- Load balancer targets unhealthy

Database
- DB down / connection refused
- DB storage 100%
- Replication lag extremely high
- Deadlocks blocking writes

Kubernetes
- CrashLoopBackOff for critical pods
- ImagePullBackOff for production workloads
- Node NotReady
- PVC not mounting for critical apps
- HPA not scaling → load failure

Security
- Secret leaked
- IAM misconfigured causing outage
- WAF blocking legitimate traffic

Third-Party
- Payment gateway outage
- SMS/Email provider down

--------------------------------------------------------

# P2 — Major Issues But Not Full Outage
========================================
Impact: Partial functionality broken, slow performance, user complaints but app still works.

Application / API
- High response time
- API timeout sometimes
- Feature-level failure (not whole app)
- CORS issues
- Cache miss causing slowness

Infrastructure
- High CPU/memory but not 100%
- Disk usage 80–90% (warning)
- EC2 instance unhealthy but ASG still serving

Networking
- Intermittent latency
- Route53 health check failing but traffic working
- WAF blocking some requests

Database
- Slow queries
- Index missing
- Connection pool nearing exhaustion
- Moderate replication lag

Kubernetes
- Pod restart frequently but serving
- Liveness/readiness probe failing intermittently
- ConfigMap/Secret updated but rollout incomplete

Security
- Token expiry issues
- TLS version mismatch warnings

CI/CD
- Deploy taking too long
- Pipeline flaky
- Non-prod build failing

--------------------------------------------------------

# P3 — Minor / Low-Priority Issues
===================================
Impact: No customer impact, cosmetic, UX issues, internal tool issues.

Application / Frontend
- UI alignment issue
- Button color mismatch
- Browser compatibility small issue
- Typo in UI

Backend
- Log format inconsistent
- Debug logs not created
- Feature toggles misconfigured (non-impacting)

Infrastructure
- CPU at 50–60%
- Disk warnings < 60%
- Non-prod server reboot required

Networking
- Latency within acceptable limits
- DNS propagation delay during new setup

Database
- Query optimization suggestions
- Table fragmentation
- Old backups cleanup required

Kubernetes
- Non-prod pods restarting
- Stale PVC in dev
- Resource requests not optimized

Security
- Non-critical vulnerability in image
- Unused permissions in IAM role

CI/CD
- Old agents offline
- Non-critical job slow
- Warnings in deployment logs
