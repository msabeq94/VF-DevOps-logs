### Query Name:  
`Remove Permission in Azure DevOps`

### Query Description:  
Monitors when permissions are removed in Azure DevOps to track changes in security settings and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Security"
| where OperationName == "Security.RemovePermission"
```

---

### Alert Name:  
`Remove Permission Alert`

### Email Subject:  
`Alert: Permission Removed in Azure DevOps`

### Email Body:  
```
Hello,

Permissions have been removed in your Azure DevOps environment.  
This action could indicate a change in security settings or configurations.

**Details:**  
- Query: Remove Permission in Azure DevOps  
- Category: Security  
- Operation(s): Remove Permission

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
