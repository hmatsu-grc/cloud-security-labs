# AWS Bucketware — AWS Credential Compromise Investigation

## Scenario Summary

An AWS identity was compromised and used to enumerate cloud resources, attempt IAM persistence, modify S3 protections, access sensitive data, and stage a ransom note.

## Investigation Objectives

- Identify the compromised AWS identity
- Reconstruct attacker reconnaissance activity
- Determine whether IAM persistence attempts succeeded
- Identify affected S3 resources
- Determine what data was accessed or modified
- Recommend remediation and security controls

## Evidence Sources

- AWS CloudTrail logs
- IAM API activity
- S3 API activity
- Source IP addresses
- Request parameters
- Error codes and API responses

## Investigation Timeline

| Time | API Call | Activity | Result |
|---|---|---|---|
| ... | ... | ... | ... |

## Key Findings

### Compromised Identity
...

### Reconnaissance Activity
...

### IAM Persistence Attempt
...

### S3 Security Changes
...

### Data Access / Exfiltration
...

## Identity and Access Analysis

Discuss:
- permissions available to the compromised user
- actions blocked by AccessDenied
- why the attacker attempted CreateUser
- whether least privilege limited the compromise

## Security Control Gaps

Discuss controls such as:
- MFA
- access key management
- least privilege
- IAM monitoring
- CloudTrail alerting
- S3 versioning protections
- GuardDuty
- anomalous API activity detection

## Remediation Recommendations

- Revoke compromised credentials
- Rotate affected access keys
- Review IAM permissions
- Remove unauthorized resources
- Restore S3 protections
- Review CloudTrail for additional malicious activity
- Enable alerting for suspicious IAM and S3 API activity

## Analyst Conclusion

Summarize the incident, impact, and whether persistence/exfiltration occurred.
