### Query Name:  
`Service Connection Created in Azure DevOps`

### Query Description:  
Monitors when a service connection is created in Azure DevOps to track new integrations and ensure secure access.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Library"
| where OperationName == "Library.ServiceConnectionCreated"
```

---

### Alert Name:  
`Service Connection Creation Alert`

### Email Subject:  
`Alert: Service Connection Created in Azure DevOps`

### Email Body:  
```
Hello,

A service connection has been created in your Azure DevOps environment.  
This action could indicate a new integration setup or configuration update.

**Details:**  
- Query: Service Connection Created in Azure DevOps  
- Category: Library  
- Operation(s): Service Connection Created

Please review this creation in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
