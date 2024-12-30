### Query Name:  
`Group Rule Modified in Azure DevOps`

### Query Description:  
Monitors when a group rule is modified in Azure DevOps to track changes in licensing assignments for user groups.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Licensing"
| where OperationName == "Licensing.GroupRuleModified"
```

---

### Alert Name:  
`Group Rule Modification Alert`

### Email Subject:  
`Alert: Group Rule Modified in Azure DevOps`

### Email Body:  
```
Hello,

A group rule has been modified in your Azure DevOps environment.  
This action could indicate a change in licensing assignments or user group configurations.

**Details:**  
- Query: Group Rule Modified in Azure DevOps  
- Category: Licensing  
- Operation(s): Group Rule Modified

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
