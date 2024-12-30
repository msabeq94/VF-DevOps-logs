### Query Name:  
`Extension Installed in Azure DevOps`

### Query Description:  
Monitors when an extension is installed in Azure DevOps to track changes in functionality and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Extension"
| where OperationName == "Extension.Installed"
```

---

### Alert Name:  
`Extension Installation Alert`

### Email Subject:  
`Alert: Extension Installed in Azure DevOps`

### Email Body:  
```
Hello,

An extension has been installed in your Azure DevOps environment.  
This action could indicate a functionality update or new integration.

**Details:**  
- Query: Extension Installed in Azure DevOps  
- Category: Extension  
- Operation(s): Extension Installed

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
