# AWS Stacked — CloudTrail Incident Investigation

## Scenario Summary

An unsuspecting cloud intern at MechZone clicks on an AWS phishing link, inadvertently deploying malicious resources into the company's cloud environment. The objective is to investigate the source of the compromise and identify the malicious resources staged by the attacker.

## Lab Setup

The challenge provides AWS CloudTrail logs from the affected environment.

### Lab Instructions

1. Become root:

```bash
sudo su
```

2. Navigate into the CloudTrail log directory:

```bash
cd /root/Desktop/ChallengeFile/AWSLogs/670756667180/CloudTrail/us-east-1/2023/06/01
```

3. Unzip the CloudTrail log files:

```bash
find . -type f -exec gunzip {} \;
```

## Investigation Objectives

The investigation aims to identify the compromised AWS identity, determine how malicious resources were deployed, analyze the resources created, review the network exposure introduced by the attacker, and identify the source of the compromise.

## Evidence Sources

- AWS CloudTrail logs
- IAM activity
- CloudFormation events
- EC2 activity
- Security group configuration
- Source IP information

## 1. Identify the Compromised Identity

### Question
What is the ARN of the compromised identity?

### Analysis

I reviewed the CloudTrail logs to identify IAM users present in the environment. Two identities were observed: `iamadmin` and `cloud-ops-intern`.

I then examined activity associated with `cloud-ops-intern`. The account was tied to suspicious resource creation activity, including `CreateUser`, `CreateSecurityGroup`, `CreateStack`, `AuthorizeSecurityGroupIngress`, and `RunInstances`.

This activity identified `cloud-ops-intern` as the compromised identity.

### Evidence

![IAM identities identified in CloudTrail logs](images/01-iam-identities.png)
![Suspicious resource creation associated with the compromised identity](images/02-compromised-identity-activity.png)

### Answer

`arn:aws:iam::670756667180:user/cloud-ops-intern`

## 2. Identify the Deployment Service

### Question
What AWS service was used to deploy malicious resources into the environment?

### Analysis

I filtered CloudTrail events associated with the compromised `cloud-ops-intern` identity for activity originating from `cloudformation.amazonaws.com`.

The logs showed a `CreateStack` event from the suspicious source IP address `31.187.69.154`, confirming that AWS CloudFormation was used to deploy the malicious resources.

### Evidence

![CloudFormation activity associated with the compromised identity](images/03-cloudformation-activity.png)

### Answer

`CloudFormation`


## 3. Identify Malicious Compute Resources

### Question
How many malicious compute resources were deployed?

### Analysis

### Evidence

### Answer


## 4. Determine the Instance Type

### Question
What is the instance type observed for these resources?

### Analysis

### Evidence

### Answer


## 5. Analyze the Malicious Security Group

### Question
What IP CIDR range did the malicious security group allow for inbound access?

### Analysis

### Evidence

### Answer


## 6. Determine the Exposed Port

### Question
What port was allowed for inbound access?

### Analysis

### Evidence

### Answer


## 7. Determine the Allowed Protocol

### Question
What protocol was allowed for inbound access?

### Analysis

### Evidence

### Answer


## 8. Identify the Malicious IAM Identity

### Question
What is the user name given to the malicious identity that was deployed?

### Analysis

### Evidence

### Answer


## 9. Determine the Attack Source

### Question
What IP address did the attack originate from?

### Analysis

### Evidence

### Answer


## Investigation Timeline

## Key Findings

## Security Control Analysis

## Remediation Recommendations

## Analyst Conclusion
