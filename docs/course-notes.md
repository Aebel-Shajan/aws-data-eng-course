
# AWS Certified Data Engineer Associate Course DEA-C01

## Contents
1. Data Engineering Fundamentals
2. Storage
3. Database
4. Migration and Transfer
5. Compute
6. Containers
7. Analytics
8. Application Integration
9. Security, Identity, and Compliance
10. Networking and Content Delivery
11. Management and Governance
12. Machine Learning
13. Developer Tools
14. Everything Else
15. Exam Tips


# 1.Data Engineering Fundamentals
Types of data:
* structured
* Unstructured
* semi structured

Properties of data:
* volumn
* velocity 
* variety

## Data Warehouse Vs Lake
Data Warehouse: Centralized repo for analysis, stored in structured format
Data Lake: Vast amount of raw data, any type. e.g. Simple Storage service s3, hdfs

Schema: schema on write (warehouse etl), schema on read (lak elt)
agility: lake > warehouse
cost: warehouse > lake

lakehouse: combination on 2 (aws lake formation)

## Data Mesh
* data management paradigm

Data sources:
* jdbc (java database connectivity)
* odbc (open database connectivity)
* raw logs
* apis


Formats: csv, json, avro, parquet

Data modeling:
## star schema:
* fact tables
* dimensions tables
* primary keys linking

## sql
aggregation:
* COUNT
* SUM
* AVG
* MAX/MIN

e.g. 
```sql
SELECT AVG(salary) AS average_salary FROM employees;
```

* aggregate with case: WHERE, CASE WHEN

* grouping: GROUP BY 

* pivoting: PIVOT ()


* ~: reqular expression operator
* ~*: case insensitive
* !~*: not ...

# 2.Storage

* Amazon s3 stands for Simple Storage Service

## S3 bucket policy
* user-based vs resource based (IAM vs bucket policies, acl)
* Examples:
    * User access to s3 -> IAM Permissions
    * EC2 instance acesss -> IAM Roles
    * Cross account access -> bucket policy

## S3 Versioning
* lets you see how files change
* deletion results in delete marker
* versioning required for crr/srr (cross region/same region replication)

## S3 Storage Classes
* Standard - General Purpose
* Standard-Infrequent Access (IA) - disaster recovery, backups
* One Zone-Infrequent Access - secondary backups, data can be created
* Glacier Instant Retrieval - once a quarter, quick acess
* Glacier Flexible Retrieval - takes longer
* Glacier Deep Archive - even longer
* Intelligent Tiering - moves object between intelligent tiering
* express one zone - good for etls/streaming

## S3 Lifecycle rules
* Transition, Expiration actions
* lets you decide what storage classes the objects have over time.

## S3 Event notifications
* events: objects removed, createded, restored, replicated
* s3 event notifications relates to iam permsiions (Resource access policy)
* events can be sent to sqs (simple queue service), sns (simple notification service) or lambda
* events can also be sent to Amazon EventBridge (which can apply rules to 18 other aws services)

hands on
* s3 bucket -> properties -> events and notifications -> create event notification
* sqs -> create queue -> queue policy -> edit access policy -> generate policy for sqs resource to detect object creation events in s3
* s3 -> create event notification with existing sqs queue


## S3 Performance
* per prefix performance
* multipart performance better
* transfer acceleration. (to public local location, privately sends to desired s3 region)
* s3 byte range fetches

## S3 object encryption
* sse (server side encryption) sse-s3, sse-kms (key management service)
* sse-c (client)
* client side encryption - encrypt before sending to s3
* DSSE-KMS "Dual layer server side encryption"

hands on 3 ways:
* Create s3 bucket with versioning on -> upload file -> edit file to use differen encryption -> creates new version of file
* default encryption type of s3 bucket
* When uploading file, there is option to set encryption type

## S3 Access points
* ways of accessing s3 buckets
* simplifies security management for s3 bucket
* each access point has individual dns

## S3 Object Lambda


