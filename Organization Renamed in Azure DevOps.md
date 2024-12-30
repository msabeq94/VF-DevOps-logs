### Query Name:  
`Organization Renamed in Azure DevOps`

### Query Description:  
Monitors when an Azure DevOps organization is renamed to track changes and maintain oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Organization"
| where OperationName == "Organization.Update.Rename"
```

---

### Alert Name:  
`Organization Renaming Alert`

### Email Subject:  
`Alert: Organization Renamed in Azure DevOps`

### Email Body:  
```
Hello,

An Azure DevOps organization has been renamed.  
This action could indicate a change in project organization or restructuring activity.

**Details:**  
- Query: Organization Renamed in Azure DevOps  
- Category: Organization  
- Operation(s): Organization Renamed

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
