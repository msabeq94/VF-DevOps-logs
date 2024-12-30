### Query Name:  
`Group Rule Deleted in Azure DevOps`

### Query Description:  
Monitors when a group rule is deleted in Azure DevOps to track changes in licensing assignments for user groups.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Licensing"
| where OperationName == "Licensing.GroupRuleDeleted"
```

---

### Alert Name:  
`Group Rule Deletion Alert`

### Email Subject:  
`Alert: Group Rule Deleted in Azure DevOps`

### Email Body:  
```
Hello,

A group rule has been deleted in your Azure DevOps environment.  
This action could indicate a change in licensing assignments or user group configurations.

**Details:**  
- Query: Group Rule Deleted in Azure DevOps  
- Category: Licensing  
- Operation(s): Group Rule Deleted

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
