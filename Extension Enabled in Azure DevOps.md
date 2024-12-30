### Query Name:  
`Extension Enabled in Azure DevOps`

### Query Description:  
Monitors when an extension is enabled in Azure DevOps to track changes in functionality and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Extension"
| where OperationName == "Extension.Enabled"
```

---

### Alert Name:  
`Extension Enabled Alert`

### Email Subject:  
`Alert: Extension Enabled in Azure DevOps`

### Email Body:  
```
Hello,

An extension has been enabled in your Azure DevOps environment.  
This action could indicate a functionality change or configuration update.

**Details:**  
- Query: Extension Enabled in Azure DevOps  
- Category: Extension  
- Operation(s): Extension Enabled

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
