
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

Amazon s3
