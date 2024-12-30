### Query Name:  
`Group Rule Created in Azure DevOps`

### Query Description:  
Monitors when a group rule is created in Azure DevOps to track changes in licensing assignments for user groups.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Licensing"
| where OperationName == "Licensing.GroupRuleCreated"
```

---

### Alert Name:  
`Group Rule Creation Alert`

### Email Subject:  
`Alert: Group Rule Created in Azure DevOps`

### Email Body:  
```
Hello,

A group rule has been created in your Azure DevOps environment.  
This action could indicate a change in licensing assignments or user group configurations.

**Details:**  
- Query: Group Rule Created in Azure DevOps  
- Category: Licensing  
- Operation(s): Group Rule Created

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
