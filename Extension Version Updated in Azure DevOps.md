### Query Name:  
`Extension Version Updated in Azure DevOps`

### Query Description:  
Monitors when an extension's version is updated in Azure DevOps to track changes in functionality and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Extension"
| where OperationName == "Extension.VersionUpdated"
```

---

### Alert Name:  
`Extension Version Update Alert`

### Email Subject:  
`Alert: Extension Version Updated in Azure DevOps`

### Email Body:  
```
Hello,

An extension version has been updated in your Azure DevOps environment.  
This action could indicate a functionality update or system change.

**Details:**  
- Query: Extension Version Updated in Azure DevOps  
- Category: Extension  
- Operation(s): Extension Version Updated

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
