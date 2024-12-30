### Query Name:  
`Group Membership Changes in Azure DevOps`

### Query Description:  
Monitors when a member is added to or removed from a group in Azure DevOps to track changes in team composition.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Group"
| where OperationName == "Group.UpdateGroupMembership.Add" or OperationName == "Group.UpdateGroupMembership.Remove"
```

---

### Alert Name:  
`Group Membership Change Alert`

### Email Subject:  
`Alert: Group Membership Changed in Azure DevOps`

### Email Body:  
```
Hello,

A group membership change has been detected in your Azure DevOps environment.  
This action could indicate a change in team composition or permissions.

**Details:**  
- Query: Group Membership Changes in Azure DevOps  
- Category: Group  
- Operation(s): Group Membership Added or Removed

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
