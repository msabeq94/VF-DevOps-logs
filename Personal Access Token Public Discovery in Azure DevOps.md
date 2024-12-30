### Query Name:  
`Personal Access Token Public Discovery in Azure DevOps`

### Query Description:  
Monitors when a Personal Access Token (PAT) is publicly discovered in Azure DevOps to ensure security and prevent unauthorized access.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Token"
| where OperationName == "Token.PatPublicDiscoveryEvent"
```

---

### Alert Name:  
`PAT Public Discovery Alert`

### Email Subject:  
`Alert: Personal Access Token Publicly Discovered in Azure DevOps`

### Email Body:  
```
Hello,

A Personal Access Token (PAT) has been publicly discovered in your Azure DevOps environment.  
This action could indicate a potential security breach or exposure of sensitive tokens.

**Details:**  
- Query: Personal Access Token Public Discovery in Azure DevOps  
- Category: Token  
- Operation(s): PAT Public Discovery

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
