### Query Name:  
`Agent Added in Azure DevOps`

### Query Description:  
Monitors when agents are added to the agent pool in Azure DevOps to track changes and additions.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Library"
| where OperationName == "Library.AgentAdded"
```

---

### Alert Name:  
`Agent Addition Alert`

### Email Subject:  
`Alert: Agent Added in Azure DevOps`

### Email Body:  
```
Hello,

An agent has been added to the agent pool in your Azure DevOps environment.  
This action could indicate a configuration update or scaling activity.

**Details:**  
- Query: Agent Added in Azure DevOps  
- Category: Library  
- Operation(s): Agent Added

Please review this addition in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
