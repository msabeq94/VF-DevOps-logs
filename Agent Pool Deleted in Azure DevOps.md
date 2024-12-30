### Query Name:  
`Agent Pool Deleted in Azure DevOps`

### Query Description:  
Monitors when an agent pool is deleted in Azure DevOps to track infrastructure changes and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Library"
| where OperationName == "LibraryAgentPoolDeleted"
```

---

### Alert Name:  
`Agent Pool Deletion Alert`

### Email Subject:  
`Alert: Agent Pool Deleted in Azure DevOps`

### Email Body:  
```
Hello,

An agent pool has been deleted in your Azure DevOps environment.  
This action could indicate a configuration update or a scaling down of resources.

**Details:**  
- Query: Agent Pool Deleted in Azure DevOps  
- Category: Library  
- Operation(s): Agent Pool Deleted

Please review this deletion in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
