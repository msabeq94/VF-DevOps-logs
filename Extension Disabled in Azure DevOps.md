### Query Name:  
`Extension Disabled in Azure DevOps`

### Query Description:  
Monitors when an extension is disabled in Azure DevOps to track changes in functionality and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Extension"
| where OperationName == "Extension.Disabled"
```

---

### Alert Name:  
`Extension Disabled Alert`

### Email Subject:  
`Alert: Extension Disabled in Azure DevOps`

### Email Body:  
```
Hello,

An extension has been disabled in your Azure DevOps environment.  
This action could indicate a functionality change or configuration update.

**Details:**  
- Query: Extension Disabled in Azure DevOps  
- Category: Extension  
- Operation(s): Extension Disabled

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
