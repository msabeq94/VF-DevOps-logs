### Query Name:  
`Personal Access Token Expired in Azure DevOps`

### Query Description:  
Monitors when a Personal Access Token (PAT) expires in Azure DevOps to ensure authentication security and identify inactive tokens.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Token"
| where OperationName == "Token.PatExpiredEvent"
```

---

### Alert Name:  
`PAT Expiration Alert`

### Email Subject:  
`Alert: Personal Access Token Expired in Azure DevOps`

### Email Body:  
```
Hello,

A Personal Access Token (PAT) has expired in your Azure DevOps environment.  
This action could indicate an authentication update or the need to renew necessary tokens.

**Details:**  
- Query: Personal Access Token Expired in Azure DevOps  
- Category: Token  
- Operation(s): PAT Expired

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
