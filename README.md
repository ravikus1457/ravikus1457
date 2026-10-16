# Ravi Kumar — Linux, networking, and cloud operations

Information Systems Technician at Contra Costa County (DNS/DHCP/AD, Palo Alto GlobalProtect VPN, Intune, PowerShell automation). Moving into cloud operations. Portfolio: **https://ravikus1457.github.io**

What I build and run, with the numbers that can be checked:

- **[fleet-ops](https://github.com/ravikus1457/fleet-ops)** — patterns from a production fleet I built and operate on a Raspberry Pi 5: **229 systemd user timers / 402 service unit files**, a 10-minute self-heal loop with restart rate-limits, failure alerting on every unit, fault-tested monitors, five dated postmortems, runbooks.
- **[aws-labs](https://github.com/ravikus1457/aws-labs)** — AWS infrastructure in Terraform with an `apply → verify → destroy` runner that captures evidence and keeps idle cost near zero: multi-AZ VPC, EC2 + ALB + Auto Scaling, least-privilege IAM + private S3, ECS Fargate with a GitHub Actions CI/CD pipeline (OIDC role, image build + ECR scan, plan → approval → apply → smoke test, nightly destroy), an **EKS cluster deployed with Helm and monitored with Prometheus, Grafana and Alertmanager** (alert rules verified by triggering them), CloudWatch alarms + SNS + Budgets. All nine labs have run on real AWS with committed evidence, including:
  - **Self-healing chaos (lab 08):** AWS FIS terminates an instance and saturates CPU while a Synthetics canary probes the site; CloudWatch alarm → EventBridge → SSM Automation runbook scales out and back. First run: instance loss **detected in 131 s, recovered 61 s later, 1 failed probe of 29**; runbook-added instance in service at 167 s.
  - **Serverless event pipeline (lab 09):** API Gateway (key + daily quota) → Lambda → SQS with DLQ and redrive → Step Functions Express → DynamoDB, traced end to end with X-Ray. **2,000-order load test: p99 386 ms, measured cost $0.03**; a poison message proven to land in the DLQ, raise the alarm and be redriven after the fix.
- **Networking labs, measured in CI** ([aws-labs/networking](https://github.com/ravikus1457/aws-labs/tree/main/networking)): real FRRouting networks built with containerlab, broken under live traffic, and measured on every push.
  - **BGP dual-ISP edge with BFD:** prefix filters, local-pref, AS-path prepending; killing the primary ISP costs **~0.3 s with BFD vs ~28.8 s on the BGP hold timer** (73/73 checks).
  - **OSPF campus + VRRP gateway pair:** pull the plug on the active core: **0.64 s user gap, 0.75 s gateway takeover, 0.1 s OSPF reroute**, takeback gated on routing (42/42).
  - **Network as code:** one YAML source of truth renders every router config; a bad PR (overlapping subnet) is **rejected before deploy**, out-of-band drift is **detected 3/3 and healed in 0.9 s** (202/202 checks).
- **[aws-ops-toolkit](https://github.com/ravikus1457/aws-ops-toolkit)** — six small boto3 operations tools (idle-resource finder, IAM key-age audit, EBS snapshot janitor, alarm bootstrap, tag sweep, notify) that print readable tables and refuse to change anything unless you say so twice.
- **[ravikus1457.github.io](https://github.com/ravikus1457/ravikus1457.github.io)** — the portfolio site (write-ups, lab index, resume).

Education: B.S. Cloud & Network Engineering, Western Governors University (in progress).

Certifications: ITIL 4 Foundation, CompTIA Security+ / Network+ / A+, Linux Essentials. AWS Solutions Architect – Associate and CloudOps Associate in progress.
