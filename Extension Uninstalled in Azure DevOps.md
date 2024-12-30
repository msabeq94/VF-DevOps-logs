### Query Name:  
`Extension Uninstalled in Azure DevOps`

### Query Description:  
Monitors when an extension is uninstalled in Azure DevOps to track changes in functionality and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Extension"
| where OperationName == "Extension.Uninstalled"
```

---

### Alert Name:  
`Extension Uninstallation Alert`

### Email Subject:  
`Alert: Extension Uninstalled in Azure DevOps`

### Email Body:  
```
Hello,

An extension has been uninstalled in your Azure DevOps environment.  
This action could indicate a functionality update or removal of an integration.

**Details:**  
- Query: Extension Uninstalled in Azure DevOps  
- Category: Extension  
- Operation(s): Extension Uninstalled

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
