### Query Name:  
`Service Connection Deleted in Azure DevOps`

### Query Description:  
Monitors when a service connection is deleted in Azure DevOps to track the removal of integrations and maintain secure access controls.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Library"
| where OperationName == "Library.ServiceConnectionDeleted"
```

---

### Alert Name:  
`Service Connection Deletion Alert`

### Email Subject:  
`Alert: Service Connection Deleted in Azure DevOps`

### Email Body:  
```
Hello,

A service connection has been deleted in your Azure DevOps environment.  
This action could indicate the removal of an integration or a configuration update.

**Details:**  
- Query: Service Connection Deleted in Azure DevOps  
- Category: Library  
- Operation(s): Service Connection Deleted

Please review this deletion in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
