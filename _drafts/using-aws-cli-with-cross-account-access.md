---
layout: post
title: Using AWS CLI with Cross-Account Access & MFA
---

Amazon Web Services(AWS) offers cloud computing services. If you are an AWS customer or your company uses AWS. There is a best practice where AWS suggests that we use multiple AWS accounts for security purposes. Typical usecase is that this allows you seperate your AWS Production and Developement Environment. If you have such a setup, chances are you will have following setup:

1. Consolidated Billing
2. Jump AWS Account which has your IAM users, permissions,groups & roles setup.
3. Multi-Factor Authentication tied to your AWS Jump Account
4. Production & Dev are Seperate Accounts configured with Cross-Account Access Role from the "Jump Aws Account"



