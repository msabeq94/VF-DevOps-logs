### Query Name:  
`SSH Key Created in Azure DevOps`

### Query Description:  
Monitors when an SSH key is created in Azure DevOps to track changes in authentication methods and ensure secure access control.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Token"
| where OperationName == "Token.SshCreateEvent"
```

---

### Alert Name:  
`SSH Key Creation Alert`

### Email Subject:  
`Alert: SSH Key Created in Azure DevOps`

### Email Body:  
```
Hello,

An SSH key has been created in your Azure DevOps environment.  
This action could indicate a change in authentication methods or new key configurations.

**Details:**  
- Query: SSH Key Created in Azure DevOps  
- Category: Token  
- Operation(s): SSH Key Created

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
