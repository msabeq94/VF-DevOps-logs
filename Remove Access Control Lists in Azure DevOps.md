### Query Name:  
`Remove Access Control Lists in Azure DevOps`

### Query Description:  
Monitors when access control lists (ACLs) are removed in Azure DevOps to track changes in security settings and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Security"
| where OperationName == "Security.RemoveAccessControlLists"
```

---

### Alert Name:  
`Remove Access Control Lists Alert`

### Email Subject:  
`Alert: Access Control Lists Removed in Azure DevOps`

### Email Body:  
```
Hello,

Access control lists (ACLs) have been removed in your Azure DevOps environment.  
This action could indicate a change in security settings or configurations.

**Details:**  
- Query: Remove Access Control Lists in Azure DevOps  
- Category: Security  
- Operation(s): Remove Access Control Lists

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
