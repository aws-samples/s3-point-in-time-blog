# Access a point-in-time with Amazon S3 Object Lambda

## Overview

Point-in-time 'snapshots' enable administrators, developers, testers, and end users to quickly access a storage volume or share how it was at an earlier point-in-time. They are a longstanding approach to data protection and recovery. However, volume-level snapshots have inherent limitations on scale, and aren't suitable for billions of objects and petabytes of data in object storage.

[Amazon S3](https://aws.amazon.com/s3/) is an object storage service with industry-leading scalability, data availability, security, performance, and 99.999999999% (11 9s) of data durability. In the [shared responsibility model](https://aws.amazon.com/compliance/shared-responsibility-model/), customers are responsible for configuring Amazon S3 to meet their security and compliance objectives. [Amazon S3 Versioning](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html) protects against accidental deletions and overwrites by keeping multiple variants of an object in the same S3 bucket. When combined with [S3 Object Lock](https://www.youtube.com/watch?v=XQVm0ebdz3E), it can also protect data against malicious activity, such as ransomware events, by preventing the removal of specific object versions. This is a threat even when using Open Table Format abstractions.

In [the blog post "Access a point-in-time with Amazon S3 Object Lambda"](https://aws.amazon.com/blogs/storage/access-a-point-in-time-with-amazon-s3-object-lambda/), we provide a snapshot-like access and recovery mechanism for Amazon S3. Deployed through [AWS CloudFormation](https://aws.amazon.com/cloudformation/), it uses [Amazon S3 Object Lambda](https://aws.amazon.com/s3/features/object-lambda/) and S3 Versioning to quickly provide one or more read-only, point-in-time views of the data in your S3 bucket, without compromising data integrity. In addition, we show how the same solution can streamline and accelerate reproduction of the entire bucket as it was at the point-in-time, in a new S3 bucket.

## Deploying

This code repository contains the YAML file *[s3-pit.yaml](s3-pit.yaml)*, which is deployed via AWS CloudFormation. For full details on how to use the solution, please see [the blog post](https://aws.amazon.com/blogs/storage/access-a-point-in-time-with-amazon-s3-object-lambda/).
