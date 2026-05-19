# aws-cloudwatch-alerts-diana
AWS CloudWatch + SNS billing alarms and S3 monitoring. Prevents surprise Free Tier charges. Built for Nigerian startups.
# DianaCloudWatch-Alerts 🚨

Cost monitoring and alerts for AWS Free Tier. Built to prevent surprise bills for Nigerian startups and learners.

## Problem
AWS Free Tier is free until it's not. One misconfiguration = $100 bill.

## Solution
Two CloudWatch alarms using SNS email notifications:

### 1. Billing Alarm — "The $1 Warning"
- **Triggers at:** $1.00 USD estimated charges
- **Action:** Sends email to me immediately  
- **Why:** Lagos startups need instant alerts, not month-end surprises
- **Tech:** CloudWatch Billing + SNS Topic

### 2. S3 Upload Alert — "Large File Warning"  
- **Triggers on:** File >5MB uploaded to `/submissions/`
- **Action:** Logs to CloudWatch + email
- **Why:** Prevents Free Tier storage abuse from v1.0 intern-policy
- **Tech:** S3 Event Notification + CloudWatch Logs

## How I Built This
1. Created SNS topic `diana-billing-alerts`
2. Subscribed my email + confirmed
3. CloudWatch → Billing Alarm → Threshold $1
4. S3 → Event → CloudWatch Logs for object size > 5MB

## What I Learned
1. **FinOps**: Monitoring is part of security. A $0 bill is secure.
2. **SNS**: Pub/sub pattern — one topic can notify email, Slack, Lambda
3. **Proactive vs Reactive**: Alert at $1, not at $100

## Cost
$0.00 — All Free Tier. SNS: 1M publishes free. CloudWatch: 10 alarms free.

## Next Learning Goal
- [ ] Add Slack webhook to SNS
- [ ] Terraform this whole setup
- [ ] Cost anomaly detection

Built by Diana | Learning AWS in Lagos, Nigeria 🇳🇬
