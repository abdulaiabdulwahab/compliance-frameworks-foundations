# compliance-frameworks-foundations

# Azure Compliance and Security Frameworks — Foundations

## Project Overview

This project demonstrates how to assess and improve Azure resource compliance using **Azure Policy** and security framework principles.

The project focuses on identifying non-compliant resources, remediating configuration issues, and collecting compliance evidence.

## Objectives

- Understand security and compliance frameworks such as NIST CSF.
- Learn how Azure Policy evaluates resource compliance.
- Create and assign a compliance policy.
- Identify non-compliant Azure resources.
- Remediate compliance findings.
- Collect evidence for security audits.

## Technologies Used

- Microsoft Azure
- Azure Policy
- Azure CLI
- Azure Storage
- NIST Cybersecurity Framework (CSF)
- Git Bash

## Project Architecture

Security Framework → Azure Policy → Azure Resource → Compliance Assessment → Remediation → Verification

## Implementation Steps

### 1. Create Azure Resources

- Created a resource group named `rg-compliance-foundations`.
- Deployed an Azure Storage account.
- Intentionally omitted the `CostCenter` tag to simulate non-compliance.

### 2. Configure Azure Policy

- Identified the built-in **Require a tag on resources** policy.
- Configured a policy assignment to assess the `CostCenter` tag.
- Used an assessment-only configuration to avoid blocking resource deployments.

A custom audit policy can also be used when the built-in policy is unavailable.

### 3. Assess Compliance

- Triggered an Azure Policy compliance evaluation.
- Reviewed the storage account's compliance status.
- Identified the missing `CostCenter` tag.

### 4. Remediate the Finding

Added the required tag:

`CostCenter=CC100`

Verified the updated resource configuration using Azure CLI.

### 5. Verify Compliance

- Triggered another compliance evaluation.
- Reviewed the updated compliance status.
- Exported before-and-after assessment evidence.

### 6. Document Results

Created a simple compliance assessment report containing:

- Security framework reference
- Technical control requirement
- Initial compliance finding
- Remediation action
- Verification evidence

## Troubleshooting

| Issue | Resolution |
|---|---|
| PolicyDefinitionNotFound | Verify the built-in policy ID or use a custom audit policy |
| No compliance results | Verify the assignment and trigger another evaluation |
| AuthorizationFailed | Verify Azure RBAC permissions |
| Resource remains non-compliant | Check resource tags and reassess |
| Storage account creation fails | Check naming requirements and inherited policies |

## Project Outcome

This project demonstrates the basic cloud compliance assessment lifecycle:

**Define Requirements → Assess Resources → Identify Findings → Remediate → Verify → Document Evidence**

It also demonstrates how Azure Policy can support organizational security requirements aligned with frameworks such as NIST CSF.

## Cleanup

After completing the project, the policy assignment and lab resource group can be deleted to avoid unnecessary Azure costs.

## Key Skills Demonstrated

- Azure governance
- Security framework fundamentals
- Azure Policy configuration
- Compliance monitoring
- Security misconfiguration remediation
- Audit evidence collection
- Cloud security best practices

## Conclusion

This project provided hands-on experience with Azure compliance assessment and security governance. It demonstrates how organizations can use automated policy checks to identify configuration gaps, improve security, and support ongoing compliance efforts.

**Note:** Passing these technical checks does not establish full compliance with a security framework.