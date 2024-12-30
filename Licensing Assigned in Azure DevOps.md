### Query Name:  
`Licensing Assigned in Azure DevOps`

### Query Description:  
Monitors when a licensing access level is assigned in Azure DevOps to track changes in user permissions and roles.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Licensing"
| where OperationName == "Licensing.Assigned"
```

---

### Alert Name:  
`Licensing Assignment Alert`

### Email Subject:  
`Alert: Licensing Assigned in Azure DevOps`

### Email Body:  
```
Hello,

A licensing access level has been assigned in your Azure DevOps environment.  
This action could indicate a user permission change or role assignment.

**Details:**  
- Query: Licensing Assigned in Azure DevOps  
- Category: Licensing  
- Operation(s): Licensing Assigned

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
