# SAP-C02

## Design Solutions for Organizational Complexity

## Design for New Solutions

## Continuous Improvement for Existing Solutions

### To save cost
- Trasnfer Cost
    - **Issue :It took more cost to transfer from AZa t AZb**
    - **Solution : To use only one AZ**
    - ELB  & VPCw
        1. It also can be happen in case of using [PrivateLink](https://aws.amazon.com/privatelink/pricing/?nc1=h_ls) Also, VPCe can be used with ELB. 
        2. [using az unique VPCe](https://docs.aws.amazon.com/vpc/latest/privatelink/manage-dns-names.html)




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



