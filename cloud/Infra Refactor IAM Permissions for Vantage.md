

## Infra Refactor IAM Permissions for Vantage

- Terraform based IAM Permissions
- Vantage User

### Backups

1. Velero :
- Implement the POC with actual Code in the DEV Environment

2.Backup IAM Policies : Daily Backups : 90 Days retain
- Scheduler => CloudBuild => Trigger => main, all environments 

iam_shelfperks-main.json
iam_shelfperks-apps-dev.json
iam_staging.json

shelfperks-backups/iam_backups/

3.Backup Secret JSON File Configuration : Daily Backups : 90 Days retain
shelfperks-main-assets/secrets

4. Backup Secret Manager variable names  (ONLY Names no needs for Values)
- Notify Slack if the Secret Manager names are missing compare to previous day

5.sp-apps-backups => Common Bucket

6. Backup Cloud Build Trigger Definitions : Weekly Schedule Trigger
Cloud export build triggers .json


### Shelfperks Prod Live Preparation :
- Merchant Portal Site
- Support Site DNS Changes


### Monitoring
Friday we can discuss on Monitoring Stuff:

- Grafana
- Prometheus
- StackDriver 
- Kibana
- Elastic Search