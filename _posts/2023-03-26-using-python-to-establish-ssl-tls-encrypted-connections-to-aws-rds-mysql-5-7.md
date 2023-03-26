---
layout: post
title: Using Python to Establish SSL/TLS Encrypted Connections to AWS RDS MySQL 5.7
date: 2023-03-26 16:54 -0500
---
Are you trying to connect to your AWS RDS MySQL database using Python? If so, you might encounter some challenges due to the additional security measures provided by AWS, such as Transport Layer Security (TLS). In this tutorial, we'll show you how to connect to your AWS RDS MySQL database on Python with TLS enabled.

## Why encrypt internal Mysql connections?
In today's security landscape, enabling encryption at all layers of an application is of utmost importance. This means that sensitive information should be encrypted in transit as well as at rest. Furthermore, it is crucial to adopt a "zero trust" approach to application security. This approach means that access to resources should not be granted based solely on the user's network location or credentials. Instead, all requests for access should be authenticated and authorized before any access is granted. This strategy helps prevent unauthorized access, reduces the risk of data breaches, and enhances overall security posture.

## Prerequisites

Before we start, make sure that you have the following:

- An AWS RDS MySQL database instance
- Python 3.x installed on your local machine
- `mysql-connector-python` package installed on your local machine
- IAM user credentials with access to your AWS RDS instance

## Enable TLS in AWS RDS

Before we can connect to our AWS RDS MySQL database with TLS enabled, we need to configure our database instance to use SSL/TLS encryption. To do this, follow these steps:

1. Log in to your AWS Management Console.
2. Navigate to the RDS service.
3. Select your MySQL instance.
4. Click on the "Modify" button.
5. Under "Advanced Settings," find the "SSL/TLS" option.
6. Set the "SSL/TLS" option to "Enabled."
7. Click on the "Continue" button and apply the changes.

Once you've completed these steps, your AWS RDS MySQL instance will be configured to use SSL/TLS encryption.

## Connect to AWS RDS MySQL on Python with TLS

To connect to our AWS RDS MySQL database on Python with TLS enabled, we need to use the `mysql-connector-python` package, which can be installed via pip:

```bash
pip install mysql-connector-python
```

Next, we need to create a Python script that connects to our AWS RDS MySQL database. Here's an example script that you can use:
<script src="https://gist.github.com/gaurish/784be8b6bf44010307fac1aaa9961fcc.js"></script>

Replace the placeholders (`<db_username>`, `<db_password>`, `<db_endpoint>`, `<db_name>`) with your own values.
Python code snippet above demonstrates how to establish a secure TLS connection to an Amazon Web Services (AWS) Relational Database Service (RDS) instance running MySQL 5.7. The code makes use of the ssl and mysql-connector-python libraries to establish the secure connection.

The code begins by importing the necessary libraries and defining the credentials and endpoint of the AWS RDS instance to which the secure connection needs to be established. The next step is specifying the path to trusted CA certificates that will be used to verify the server's identity. This trusted CA certificate is provided by AWS RDS on their documentation page.

Once the SSL context has been created, the mysql-connector-python library is used to create a connection object that uses the SSL context to establish a secure connection to the AWS RDS instance. The code then prints the version of the MySQL server that it has connected to, which serves as a confirmation that the secure connection has been established successfully.

## Documentation Links

- [AWS Doc - Using SSL/TLS to encrypt a connection to a DB instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.SSL.html)
- [Official docs for Python lib from Mysql](https://dev.mysql.com/doc/connector-python/en/connector-python-introduction.html)

Hope this helps!


