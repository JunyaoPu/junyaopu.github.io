---
layout: single
title:  "AI Dev Day 2: Set up AWS S3 with an EC2 instance"
date:   2022-05-02- 00:43:00 -0500
categories: AI
collection: AI
classes: wide
header:
    teaser: /assets/images/ai_day2/post_ai_s3.png
---

# To set up AWS S3 with an EC2 instance
1.Create an S3 bucket to store the data you wish to transfer.

2.Connect to your EC2 instance using SSH.

3.Install the AWS CLI on your EC2 instance.

4.Configure the AWS CLI with your AWS Access Key and Secret Access Key.

5.Test the connection by running a simple AWS CLI command, such as "aws s3 ls".

6.Use AWS CLI commands to transfer files between your EC2 instance and S3 bucket.

## To upload a file to S3 from EC2
```
aws s3 cp /path/to/local/file s3://my-bucket/path/to/s3/file
```

## To download a file from S3 to EC2
```
aws s3 cp s3://my-bucket/path/to/s3/file /path/to/local/file
```
