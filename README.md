# ETL off an AWS SQS Queue

Writing an application that can read from an AWS SQS Queue, transform that data, and then write to a Postgres database.


## Objectives

1. Read JSON data containing user login behavior from an AWS SQS Queue, that is made
available via a custom localstack image that has the data pre-loaded.
2. Hiding personal identifiable information (PII). The fields `device_id` and `ip`
should be masked, but in a way where it is easy for data analysts to identify duplicate
values in those fields.
3. Writing each record to a Postgres database that is made available via a custom postgres image that
has the tables pre-created.

## Setup

### 1. Installing Docker

Navigate to the Docker [website](https://docs.docker.com/get-docker/) and follow the instructions to install Docker on your respective platform. After installing, make sure it works by typing the following command into your terminal:

```
which docker
```

If Docker is installed correctly, you should get a response that looks similar to `/usr/local/bin/docker`

### 2. Installing AWS CLI

Use the following code to install the AWS CLI on your platform:

```
pip install awscli-local
```

### 3. Installing PostgreSQL

You can find instructions to downloading PostgreSQL on their [website](https://www.postgresql.org/download/).

The simplest method is to first download the app [here](https://postgresapp.com/downloads.html). Then run commands to configure $PATH by following the instructions [here](https://postgresapp.com/documentation/cli-tools.html).

## Step 1: Downloading Docker Imgages

There are two Docker Images with pre-loaded test data that we need to run the application. These two Docker Images contain the SQS server and the Postgres Server, respectively. Download both by running the following commands on your terminal:

```
docker pull fetchdocker/data-takehome-postgres
```

```
docker pull fetchdocker/data-takehome-localstack
```


