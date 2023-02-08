---
layout: single
title:  "AI Dev Day 2: Setup AWS S3 with an EC2 instance"
date:   2022-05-02- 00:43:00 -0500
categories: AI
collection: AI
classes: wide
header:
    teaser: /assets/images/ai_day2/post_ai_s3.png
---
# Motivation  
When developing AI projects on the cloud, we often need to transfer trained models or large datasets to the cloud server. The simplest way to transfer files is by using SCP, but it can be too slow for transferring files with multiple gigabytes in size. By utilizing an AWS S3 bucket with the awscli, we can effectively transfer and store large files in the S3 bucket.

# The pipeline

## Install AWS CLI

```
sudo apt-get update
sudo apt-get install awscli
aws  --version
```

## Create an access key ID on AWS
<a href="https://docs.aws.amazon.com/powershell/latest/userguide/pstools-appendix-sign-up.html">AWS Account and Access Keys</a>

1 Open the IAM console at <a href="https://console.aws.amazon.com/iam/">the IAM console</a>

2 On the navigation menu, choose Users.

3 Choose your IAM user name (not the check box).

4 Open the Security credentials tab, and then choose Create access key.

5 To see the new access key, choose Show. Your credentials resemble the following:

6 To download the key pair, choose Download .csv file. Store the .csv file with keys in a secure location.

## Configure AWS access on your system

```
aws configure
```

## To upload a file to S3 from EC2
```
aws s3 cp /path/to/local/file s3://my-bucket/path/to/s3/file
```

## To sync a file to S3 from EC2
```
aws s3 cp sync /path/to/local/file s3://my-bucket/path/to/s3/file
```

## To download a file from S3 to EC2
```
aws s3 cp s3://my-bucket/path/to/s3/file /path/to/local/file
```
# Achievements
After reading the post and information provided in the links

* You should be able to transfer files efficiently and freely between your local/cloud machine and an AWS S3 bucket.

# What's next
Now that we have set up a cloud storage and machine on AWS, let's dive into deep learning!

