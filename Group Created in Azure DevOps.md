### Query Name:  
`Group Created in Azure DevOps`

### Query Description:  
Monitors when a group is created in Azure DevOps to track new team setups and configurations.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Group"
| where OperationName == "Group.CreateGroups"
```

---

### Alert Name:  
`Group Creation Alert`

### Email Subject:  
`Alert: Group Created in Azure DevOps`

### Email Body:  
```
Hello,

A group has been created in your Azure DevOps environment.  
This action could indicate a new team setup or configuration activity.

**Details:**  
- Query: Group Created in Azure DevOps  
- Category: Group  
- Operation(s): Group Created

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
