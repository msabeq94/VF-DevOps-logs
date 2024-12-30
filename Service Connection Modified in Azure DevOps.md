### Query Name:  
`Service Connection Modified in Azure DevOps`

### Query Description:  
Monitors when a service connection is modified in Azure DevOps to track configuration updates and maintain secure access controls.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Library"
| where OperationName == "Library.ServiceConnectionModified"
```

---

### Alert Name:  
`Service Connection Modification Alert`

### Email Subject:  
`Alert: Service Connection Modified in Azure DevOps`

### Email Body:  
```
Hello,

A service connection has been modified in your Azure DevOps environment.  
This action could indicate a configuration update or a change in access settings.

**Details:**  
- Query: Service Connection Modified in Azure DevOps  
- Category: Library  
- Operation(s): Service Connection Modified

Please review this modification in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
