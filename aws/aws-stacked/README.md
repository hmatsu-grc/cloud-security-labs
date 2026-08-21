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

## Evidence Sources

## 1. Identify the Compromised Identity

## 2. Establish Authentication Context

## 3. Trace CloudFormation Activity

## 4. Identify Malicious Compute Resources

## 5. Analyze Security Group Changes

## 6. Identify Malicious IAM Resources

## 7. Determine the Attack Source

## Investigation Timeline

## Key Findings

## Security Control Analysis

## Remediation Recommendations

## Analyst Conclusion
