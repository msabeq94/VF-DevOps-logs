### Query Name:  
`Personal Access Token Created in Azure DevOps`

### Query Description:  
Monitors when a Personal Access Token (PAT) is created in Azure DevOps to track changes in authentication methods and ensure proper security oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Token"
| where OperationName == "Token.PatCreateEvent"
```

---

### Alert Name:  
`PAT Creation Alert`

### Email Subject:  
`Alert: Personal Access Token Created in Azure DevOps`

### Email Body:  
```
Hello,

A Personal Access Token (PAT) has been created in your Azure DevOps environment.  
This action could indicate a change in authentication methods or configurations.

**Details:**  
- Query: Personal Access Token Created in Azure DevOps  
- Category: Token  
- Operation(s): PAT Created

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
