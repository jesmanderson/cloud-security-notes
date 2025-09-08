# Identity and Access Management (IAM) 

## What is IAM?
**IAM is the gatekeeper of your cloud environment.**  

Identity and Access Management (IAM) is the framework of policies and technologies that ensures the **right people and systems have the right access at the right time**.

Basically, it controls:

- **Who** can access your cloud resources
- **What** they can do
- **When** and **how** they can do it

## Key Concepts
- **Principals:** Users, groups, roles, or services that request access.
- **Authentication:** Verifying identity (passwords, MFA, keys).
- **Authorization:** Defining what actions are allowed.
- **Policies:** JSON documents that grant/deny permissions.
- **Least Privilege:** Grant only the access required to perform a task.

## Goals
- Prevent unauthorized access.
- Enforce least privilege.
- Enable accountability (audit logs).
- Support secure scaling of users and apps.

## Best Practices
- Enable MFA for all users.
- Use **roles** instead of long-term access keys.
- Apply least privilege with scoped policies.
- Rotate credentials regularly.
- Monitor and log all access.

## Examples
- ❌ **Bad policy:**  
  ```json
  { "Effect": "Allow", "Action": "*", "Resource": "*" }

- ✅ **Better policy:**  
  ```json
  { "Effect": "Allow", "Action": ["s3:GetObject","s3:PutObject"], "Resource": "arn:aws:s3:::mybucket/*" } 
  ```

## Mapping Standards 
- NIST 800-53: AC-2, AC-6
- CIS Controls: 6.1, 6.2
- SOC 2: CC6.1 

## As a Cloud Security Engineer, My IAM Goals are:
1. **Least Privilege Access**: Users/apps should only get the permissions they *need*, and nothing more.
2. **Separation of Duties**: No single account should have too much power.
3. **Visibility + Auditing**: Every action is logged, traceable, and reviewable.
4. **Secure Authentication**: Strong auth methods, especially for privileged access (MFA, identity federation).
5. **Automated Lifecycle**: Permissions should adjust or expire based on user/job status (joiner/mover/leaver model). 

## AWS IAM Key Concepts
| Term	    | What It Means |     
| --------- | ------------  | 
| IAM Users	| Cloud identities for people or apps | 
| IAM Groups| Collections of users with the same policies | 
| IAM Roles	| Temporary identities for resources/services | 
| Policies	| JSON documents that define permissions | 
| STS   	| Security Token Service — for short-lived credentials | 

### Example:
- A **DevOps engineer** might be in a group with *read/write access* to S3 buckets, but **no admin access**.
- A **Lambda function** might assume a **role** that lets it only write logs to CloudWatch.

## Azure IAM Key Concepts 
| Term      |  What It Means |
| --------- | ---------- | 
| Azure AD Users | 	Identities synced from your org or created in Azure|
| Roles | 	Define sets of permissions (RBAC)|
| Role Assignments | 	Link a user/group to a role in a specific scope (e.g., subscription,resource group, resource) |
| Privileged Identity Management (PIM)	|  Just-in-time access with approvals/logs|
| Conditional Access	|  Enforce access policies based on risk (location, device, etc.)|

## IAM Scenarios I Handle as a Cloud Security Engineer 
| Scenario	| What You Do |
| --------- | ---------- | 
| Enforcing MFA	|Require MFA for console & CLI access, especially for admins
| Overprivileged roles |	Audit users/roles with AdministratorAccess and replace with least privilege
| IAM lifecycle automation |	Use SCIM/HR feeds to automatically update or revoke access
| Log analysis	| Use AWS CloudTrail or Azure Activity Logs to detect risky IAM events
| Securing service accounts	| Rotate access keys, use roles with short-lived tokens
| Access reviews	| Work with HR/compliance to verify users still need access (e.g., quarterly reviews) | 

## IAM Best Practices Checklist 
- [ ]  **No root account usage** (AWS) / Global Admin overuse (Azure)
- [ ]  **MFA for all users**
- [ ]  **Separate human and machine identities**
- [ ]  **Use roles instead of long-term credentials**
- [ ]  **Log and monitor all IAM activity**
- [ ]  **Automate provisioning/deprovisioning**
- [ ]  **Run regular access reviews & audits**

## Tools That Help
- **AWS IAM Access Analyzer** – Flags excessive permissions
- **Azure PIM + Defender for Cloud** – Just-in-time & threat protection
- **HashiCorp Vault** – Secrets management
- **Cloud Custodian / AWS Config / Azure Policy** – Automated governance
- **SCIM / Okta / Azure AD** – Identity lifecycle automation 

## References 
https://learn.microsoft.com/en-us/entra/fundamentals/identity-fundamental-concepts 
https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html
https://docs.aws.amazon.com/IAM/latest/UserGuide/security-creds-programmatic-access.html
https://microsoftlearning.github.io/AZ500-AzureSecurityTechnologies/ 
