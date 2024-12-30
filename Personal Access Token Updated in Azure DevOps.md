### Query Name:  
`Personal Access Token Updated in Azure DevOps`

### Query Description:  
Monitors when a Personal Access Token (PAT) is updated in Azure DevOps to track changes in authentication methods and ensure security compliance.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Token"
| where OperationName == "Token.PatUpdateEvent"
```

---

### Alert Name:  
`PAT Update Alert`

### Email Subject:  
`Alert: Personal Access Token Updated in Azure DevOps`

### Email Body:  
```
Hello,

A Personal Access Token (PAT) has been updated in your Azure DevOps environment.  
This action could indicate a change in authentication methods or token configurations.

**Details:**  
- Query: Personal Access Token Updated in Azure DevOps  
- Category: Token  
- Operation(s): PAT Update

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
