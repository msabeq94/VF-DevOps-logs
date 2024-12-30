### Query Name:  
`SSH Key Revoked in Azure DevOps`

### Query Description:  
Monitors when an SSH key is revoked in Azure DevOps to track changes in authentication methods and ensure secure access control.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Token"
| where OperationName == "Token.SshRevokeEvent"
```

---

### Alert Name:  
`SSH Key Revocation Alert`

### Email Subject:  
`Alert: SSH Key Revoked in Azure DevOps`

### Email Body:  
```
Hello,

An SSH key has been revoked in your Azure DevOps environment.  
This action could indicate a change in authentication methods or removal of unused keys.

**Details:**  
- Query: SSH Key Revoked in Azure DevOps  
- Category: Token  
- Operation(s): SSH Key Revoked

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
