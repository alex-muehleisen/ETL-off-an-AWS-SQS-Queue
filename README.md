# ETL off an AWS SQS Queue

Writing an application that can read from an AWS SQS Queue, transform that data, and then write to a Postgres database.


## Objectives

1. Read JSON data containing user login behavior from an AWS SQS Queue, that is made
available via a custom localstack image that has the data pre-loaded.
2. Hiding personal identifiable information (PII). The fields `device_id` and `ip`
should be masked, but in a way where it is easy for data analysts to identify duplicate
values in those fields.
3. Writing each record to a Postgres database that is made available via a custom postgres image that
has the tables pre-created

## Setup

### 1. Installing Docker

Navigate to the Docker [website](https://docs.docker.com/get-docker/) and follow the instructions to install Docker on your respective platform.

### 2. Installing AWS CLI

Use the following code to install the AWS CLI on your platform:

```
pip install awscli-local
```

If you have any issues, refer to this Stack Overflow page: 


