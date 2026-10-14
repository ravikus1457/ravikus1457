# Ravi Kumar — Linux, networking, and cloud operations

Information Systems Technician at Contra Costa County (DNS/DHCP/AD, Palo Alto GlobalProtect VPN, Intune, PowerShell automation). Moving into cloud operations. Portfolio: **https://ravikus1457.github.io**

What I build and run, with the numbers that can be checked:

- **[fleet-ops](https://github.com/ravikus1457/fleet-ops)** — patterns from a production fleet I built and operate on a Raspberry Pi 5: **229 systemd user timers / 402 service unit files**, a 10-minute self-heal loop with restart rate-limits, failure alerting on every unit, fault-tested monitors, five dated postmortems, runbooks.
- **[aws-labs](https://github.com/ravikus1457/aws-labs)** — AWS infrastructure in Terraform with an `apply → verify → destroy` runner that captures evidence and keeps idle cost near zero: multi-AZ VPC, EC2 + ALB + Auto Scaling, least-privilege IAM + private S3, ECS Fargate with a GitHub Actions CI/CD pipeline (OIDC role, image build + ECR scan, plan → approval → apply → smoke test, nightly destroy), an **EKS cluster deployed with Helm and monitored with Prometheus, Grafana and Alertmanager** (alert rules verified by triggering them), CloudWatch alarms + SNS + Budgets.
- **[aws-ops-toolkit](https://github.com/ravikus1457/aws-ops-toolkit)** — six small boto3 operations tools (idle-resource finder, IAM key-age audit, EBS snapshot janitor, alarm bootstrap, tag sweep, notify) that print readable tables and refuse to change anything unless you say so twice.
- **[ravikus1457.github.io](https://github.com/ravikus1457/ravikus1457.github.io)** — the portfolio site (write-ups, lab index, resume).

Education: B.S. Cloud & Network Engineering, Western Governors University (in progress).

Certifications: ITIL 4 Foundation, CompTIA Security+ / Network+ / A+, Linux Essentials. AWS Solutions Architect – Associate and CloudOps Associate in progress.
