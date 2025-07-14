# SAP-C02

## Design Solutions for Organizational Complexity

### Irregular usage
- ECS is useful for divide task into container
    - [Beanstalk](https://aws.amazon.com/jp/elasticbeanstalk/) is the servie to manage execute and deploy

### Update Old Organizations to New Organizations
- ```RemoveAccountFromOrganization``` before account join new org
- ```InviteAccountToOrganization``` for inviting account

### DNS Resolve in Onpremse to AWS
- AWS into Onpremise : [Outbound Resolver](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resolver.html)
- Onpremise into AWS : Inbound Resolver

### Control the organization access
- [Use SCP of Org](https://docs.aws.amazon.com/ja_jp/organizations/latest/userguide/orgs_manage_policies_scps.html)

## Design for New Solutions

### Integrate Exisiting App into AWS

- [AWS Migration Hub](https://docs.aws.amazon.com/migrationhub/latest/ug/whatishub.html)
    - It is useful tracking Transferring Plan. inspect existing server.
- [AWS Application Migration Service](https://aws.amazon.com/jp/application-migration-service/)
    - Service for transferring onpremise service into AWS Cloud

### MQTT Protocol
- [IoT Core](https://docs.aws.amazon.com/iot/latest/developerguide/what-is-aws-iot.html)
    - Full Managed Service
- MQ
    - When to keep high availability, you should consider network configuration.

### Access S3 from Onpremise without using public internet
- [S3 Interface endpoint use private ip address](https://docs.aws.amazon.com/ja_jp/AmazonS3/latest/userguide/privatelink-interface-endpoints.html)
- Gateway endpoint not allow to get access from onpremise and other region.

### Trasfer file via SFTP
- [AWS Trnasfer Family](https://docs.aws.amazon.com/transfer/latest/userguide/what-is-aws-transfer-family.html)
    - This Service make it easy to trasnsfer file into AWS storage servie
    - automatically create SFTP Server

### Backup
- [AWS Backup - Cross Region Supported](https://docs.aws.amazon.com/aws-backup/latest/devguide/cross-region-backup.html)
- [Notifications](https://docs.aws.amazon.com/aws-backup/latest/devguide/backup-notifications.html)
    - In case of RDS, there are part of manual step.

#### In case of Aurora
- Global Database will recovery within less than 1s

### Disaster Ricovery
- [Elastic Disaster Ricovery](https://docs.aws.amazon.com/drs/latest/userguide/what-is-drs.html)
    - To recovery minimal compute and storage
- Amazon FSx for Lustre -> Linux base FSX
- [AWS DataSync](https://docs.aws.amazon.com/datasync/latest/userguide/what-is-datasync.html)
    - Able to failover and failback
    - Transfer data to cloud

- Route 53 [Failover routing policy](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html#routing-policy-failover)

### Allow other account to use my account in Org
- invoke ```OrganizationAccountAccessRole``` from other account


## Continuous Improvement for Existing Solutions
### Check security in CodeCommit
- [Use CodeCommit Triger and Lambda function](https://docs.aws.amazon.com/codecommit/latest/userguide/how-to-notify-lambda.html)
- [Amazon Macie](https://aws.amazon.com/jp/macie/) is to check the security in Amazon Macie

### Monitoring the situation EC2 access 
- [VPC Flow Log](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html)
    - check traffice between EC2 and onpremise

### To save cost
- Trasnfer Cost
    - **Issue :It took more cost to transfer from AZa t AZb**
    - **Solution : To use only one AZ**
    - ELB  & VPCw
        1. It also can be happen in case of using [PrivateLink](https://aws.amazon.com/privatelink/pricing/?nc1=h_ls) Also, VPCe can be used with ELB. 
        2. [using az unique VPCe](https://docs.aws.amazon.com/vpc/latest/privatelink/manage-dns-names.html)

### Blue/Green Deployment for Elastic Beanstalk
- [Swap Environmnet URLs](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.CNAMESwap.html)



## Accelerate Workload Migration and Modernization

### Database Migration
- Oracle
Data Pump is useful to migrate directoly
    - [Oracle Data Pump](https://docs.oracle.com/cd/F19136_01/sutil/oracle-data-pump-overview.html#GUID-17FAE261-0972-4220-A2E4-44D479F519D4)
    - [Amazon RDS for Oracle](https://aws.amazon.com/rds/oracle/)
    - [DMS (Other pattern)](https://aws.amazon.com/jp/dms/)

### Onpremise to AWS Cloud
- issue : Backup to AWS Cloud for every day
- solution : select most cost optimized way
    - [Storage Gateway](https://docs.aws.amazon.com/storagegateway/)
        - File Gateway : to use for FileStorage by using NFS etc
        - FSx : to use for DataAnalytics
        - Storage Gateway : to use for BlockStorage

### When using exisisting AD
- use [AWS IAM Identity Center](https://docs.aws.amazon.com/singlesignon/latest/userguide/manage-your-identity-source-idp.html)


