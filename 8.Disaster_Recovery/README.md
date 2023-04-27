# Disaster Recovery

- RTO: Recovery Time Objective
- RPO: Recovery Point Objective

4 Techniques for backup and disaster recovery:
- Backup and Recovery
- Pilot Light
- Warm Standby
- Hot Standby/Multisite

1. Backup and Recovery

- Data backed to tape and sent off site
- Uploaded to S3 for high RPO - Recovery Point Objective (RPO)
- Alternatively may use Snapshots

2. Pilot Light

- Run smaller system version
- Quick to recover, restores more data than backup and recovery

3. Warm Standby

- Full system running at minimum size
- Recovery Time Objective (RTO) approximately 0
- Expensive
- Use scaling to bring into production

4. Hot Standby

- Very expensive
- App running, possibly in different region
- S3 weighted routing