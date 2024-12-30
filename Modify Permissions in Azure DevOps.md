### Query Name:  
`Modify Permissions in Azure DevOps`

### Query Description:  
Monitors when permissions are modified in Azure DevOps to track changes in security settings and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Security"
| where OperationName == "Security.ModifyPermission"
```

---

### Alert Name:  
`Modify Permission Alert`

### Email Subject:  
`Alert: Permissions Modified in Azure DevOps`

### Email Body:  
```
Hello,

Permissions have been modified in your Azure DevOps environment.  
This action could indicate a change in security settings or configurations.

**Details:**  
- Query: Modify Permissions in Azure DevOps  
- Category: Security  
- Operation(s): Modify Permission

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
