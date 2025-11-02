# FULL LIST OF APPLICATION ISSUES (REAL-WORLD)
==============================================

1. Infrastructure Issues
- Server down / crashed
- High CPU
- High memory usage (OOMKill)
- Disk full
- Network bandwidth exhausted
- Kernel panic
- OS patching issues
- Node NotReady (K8s)
- Wrong instance type / insufficient resources
- Auto-scaling group not scaling

2. Networking Issues
- Unable to connect to application
- Port not open
- SG/Firewall rules blocking traffic
- Network latency / spike
- IP conflict
- Misconfigured NACL
- DNS not resolving
- SSL handshake failure
- Cross-VPC/peering issues
- VPN/Direct Connect issues

3. Load Balancer Issues
- 4xx/5xx errors
- Target group health check failing
- Wrong protocol / ports
- Sticky session misconfigured
- Listener rules incorrect
- ALB WAF blocking traffic
- Not enough capacity

4. API Issues
- API timeout
- 500 internal server error
- Rate-limit exceeded
- Dependency API down
- Authentication token expired / invalid
- Wrong payload schema
- CORS error
- Slow response time

5. Application Issues (Backend)
- Null pointer exception
- Unhandled exceptions
- Memory leak in code
- Connection pool exhaustion
- Too many threads
- Deadlock
- Dependency library mismatch
- Misconfigured environment variables
- Wrong file / folder permissions
- Application restart loop

6. Frontend Issues
- Browser caching issues
- JavaScript errors
- CSS not loading
- API request blocked
- Build failing
- UI not rendering on some devices
- CDN cache stale / missing

7. Database Issues
- Connection refused
- Too many connections
- Slow queries
- Deadlocks
- Table lock
- Index missing (slow performance)
- Database full (storage)
- Replication lag
- Backup failure
- Corrupted data
- Schema version mismatch

8. Caching Issues (Redis, Memcached)
- Cache miss → slow performance
- Redis connection timeout
- Cache expired too soon
- Stale cache
- Out-of-memory eviction
- Cluster failover

9. Message Queue Issues (SQS, Kafka, RabbitMQ)
- Messages stuck
- Consumer lag
- Dead-letter queue filling
- Message duplication
- Partition leader loss (Kafka)
- Consumer crash

10. Deployment / CI-CD Issues
- Build failure
- Image push failure
- Terraform stuck
- Wrong version deployed
- Missing secret in pipeline
- Rollback failed
- Agent offline
- Incorrect environment variable
- Jenkins shared library error

11. Kubernetes Issues
- Pod CrashLoopBackOff
- ImagePullBackOff
- Container OOMKilled
- Node NotReady
- PVC not bound
- Service not reachable
- ConfigMap / Secret not loaded
- HPA not scaling
- Kube-proxy failure
- NetworkPolicy blocking traffic

12. Storage Issues
- Disk IOPS throttling
- EBS volume full
- EFS mount timeout
- PVC stuck in Pending
- Data corruption

13. Logging & Monitoring Issues
- Logs not collected
- Loki / ELK ingestion full
- Wrong log format
- No alerts configured
- Too many alerts (noise)
- Metrics missing

14. Security Issues
- Expired SSL certificate
- Secret leaked
- IAM misconfigured
- Unauthorized access
- WAF rules blocking traffic
- JWT token invalid
- Vulnerabilities in image

15. DNS Issues
- New domain not resolving
- Wrong CNAME or A record
- TTL too high (delays)
- Route53 health checks failing
- Split-horizon DNS issues

16. Third-Party Dependency Issues
- Payment gateway down
- SMS / Email provider slow
- OAuth provider outage
- External API rate limiting

17. Performance Issues
- High latency
- Throughput drops
- High error rate
- Slow DB queries
- CPU throttling
- Cold start in Lambda

18. Configuration Issues
- Wrong secret
- Wrong DB credentials
- Wrong endpoint
- Misconfigured config file
- YAML indentation issue
- Incorrect feature flag

19. Resource Exhaustion
- Thread exhaustion
- File descriptor limit exhausted
- Connection pool full
- Disk inode full

20. User-Side Issues
- Browser issue
- Incorrect input
- Local network slow
- VPN blocking request
