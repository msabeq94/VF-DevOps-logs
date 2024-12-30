### Query Name:  
`Organization Deleted in Azure DevOps`

### Query Description:  
Monitors when an Azure DevOps organization is deleted to track deprovisioning and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Organization"
| where OperationName == "Organization.Update.Delete"
```

---

### Alert Name:  
`Organization Deletion Alert`

### Email Subject:  
`Alert: Organization Deleted in Azure DevOps`

### Email Body:  
```
Hello,

An Azure DevOps organization has been deleted.  
This action could indicate deprovisioning activity or a potential misconfiguration.

**Details:**  
- Query: Organization Deleted in Azure DevOps  
- Category: Organization  
- Operation(s): Organization Deleted

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
