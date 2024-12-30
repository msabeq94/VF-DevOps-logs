### Query Name:  
`Licensing Removed in Azure DevOps`

### Query Description:  
Monitors when a licensing access level is removed in Azure DevOps to track changes in user permissions and roles.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Licensing"
| where OperationName == "Licensing.Removed"
```

---

### Alert Name:  
`Licensing Removal Alert`

### Email Subject:  
`Alert: Licensing Removed in Azure DevOps`

### Email Body:  
```
Hello,

A licensing access level has been removed in your Azure DevOps environment.  
This action could indicate a change in user permissions or role assignments.

**Details:**  
- Query: Licensing Removed in Azure DevOps  
- Category: Licensing  
- Operation(s): Licensing Removed

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
