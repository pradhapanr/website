---
layout: page
title: AWS SAM
description: Making cloud scalable solutions easy for GraphQL devs.
img: assets/img/sam.png
importance: 1
---

During my second internship at AWS from January to April in 2023, I built GraphQL tooling (AppSync) for AWS Serverless
Application Model (SAM). SAM is an open-source framework for building serverless applications, which provides an extension of
the CloudFormation syntax for provisioning services with best built-in pracices and sane defaults. With SAM, CloudFormation
users can see a 90% reduction in template sizes, and overall simplification of IaC solutions.

One of our main focuses was reducing the complexity of creating AppSync resources in CloudFormation. There were multiple types
of resources in standard CFN that needed to link to each other with intrinsics, which lead to some really weird looking templates. This was a vocalized issue from AppSync users, so we decided to stick with one primary resource,
`AWS::Serverless::GraphQLApi`.
