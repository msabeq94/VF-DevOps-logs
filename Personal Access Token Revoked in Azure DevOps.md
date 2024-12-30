### Query Name:  
`Personal Access Token Revoked in Azure DevOps`

### Query Description:  
Monitors when a Personal Access Token (PAT) is revoked in Azure DevOps to track changes in authentication methods and ensure security compliance.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Token"
| where OperationName == "Token.PatRevokeEvent"
```

---

### Alert Name:  
`PAT Revocation Alert`

### Email Subject:  
`Alert: Personal Access Token Revoked in Azure DevOps`

### Email Body:  
```
Hello,

A Personal Access Token (PAT) has been revoked in your Azure DevOps environment.  
This action could indicate a change in authentication methods or deactivation of unused tokens.

**Details:**  
- Query: Personal Access Token Revoked in Azure DevOps  
- Category: Token  
- Operation(s): PAT Revocation

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
