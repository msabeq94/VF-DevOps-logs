### Query Name:  
`Group Deleted in Azure DevOps`

### Query Description:  
Monitors when a group is deleted in Azure DevOps to track team deprovisioning and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Group"
| where OperationName == "Group.UpdateGroups.Delete"
```

---

### Alert Name:  
`Group Deletion Alert`

### Email Subject:  
`Alert: Group Deleted in Azure DevOps`

### Email Body:  
```
Hello,

A group has been deleted in your Azure DevOps environment.  
This action could indicate a team deprovisioning activity or configuration update.

**Details:**  
- Query: Group Deleted in Azure DevOps  
- Category: Group  
- Operation(s): Group Deleted

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
