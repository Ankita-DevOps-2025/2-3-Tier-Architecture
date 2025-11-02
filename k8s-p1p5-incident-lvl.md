# INCIDENT SEVERITY LEVELS IN KUBERNETES (P1–P5)
================================================

# P1 – CRITICAL / SEVERITY 1
--------------------------
Meaning:
- Full production outage
- Major business impact
- Needs immediate on-call response

Examples in Kubernetes/EKS:
- API Server down → kubectl not working, no deployments possible
- Ingress/ALB/NLB down → all traffic failing
- ETCD failure → cluster unable to read/write state
- All pods crashlooping due to config push
- All nodes NotReady (autoscaler or CNI corruption)

Incident Response:
- War room opened
- On-call SRE + DevOps + developers join
- Rollback, restore, or failover immediately
- Continuous updates (every 15 min)

------------------------------------------------

# P2 – HIGH
----------
Meaning:
- Production degraded
- Partial service outage
- Users impacted but system not fully down

Examples:
- One node down → workloads rescheduled but performance degraded
- Deployment stuck → cannot deploy new version
- High latency due to HPA/CNI issue
- PersistentVolume failing to mount for some pods
- One customer namespace down (multi-tenant cluster)

Incident Response:
- High priority fix
- Action within 30–60 minutes
- No war room unless escalated

------------------------------------------------

# P3 – MEDIUM
------------
Meaning:
- Moderate impact
- Mostly non-prod or partial prod impact
- Can be handled during business hours

Examples:
- Logging issue (Fluent Bit / EFK / CloudWatch logs not updating)
- Resource quota reached in namespace
- ConfigMap updated but pods not restarted
- HPA scaling slowly
- Dev/staging environment down

Incident Response:
- Assigned to engineering team
- Fix within same day or next sprint if minor

------------------------------------------------

# P4 – LOW
---------
Meaning:
- Cosmetic or minor issue
- No customer impact
- Can be scheduled later

Examples:
- Dashboard UI showing wrong metrics
- Kubernetes version upgrade planning
- Unused PVC cleanup
- Non-critical Helm chart warnings

Incident Response:
- Planned in backlog
- No urgency
- Normal SLA (days to weeks)

------------------------------------------------

# P5 – VERY LOW / REQUEST
------------------------
Meaning:
- Enhancement, documentation, or feature request
- No urgency

Examples:
- Update Helm chart structure
- Add new namespace for a team
- Add labels/annotations to pods
- Request for RBAC role creation (not urgent)

Incident Response:
- Normal sprint planning
- No SLA pressure
- Treated as improvement task

------------------------------------------------

# QUICK SUMMARY TABLE
-------------------
| Priority | Description       | Typical Issues in K8s/EKS                    | Response Urgency    |
|-----------|------------------|----------------------------------------------|---------------------|
| P1        | Critical outage   | Cluster down, API/ETCD failure, ingress down | Immediate, war-room |
| P2        | Major degradation | Node failure, PV issues, rollout stuck       | Within 1 hour       |
| P3        | Minor degradation | Logging, HPA delay, dev env issues           | Same day            |
| P4        | Low impact        | Warnings, cleanup, small bugs                | Days                |
| P5        | Request           | Enhancements, documentation, requests        | Weeks / next sprint |
