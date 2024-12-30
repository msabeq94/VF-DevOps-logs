### Query Name:  
`Agent Deleted in Azure DevOps`

### Query Description:  
Monitors when agents are removed from the agent pool in Azure DevOps to track deletions and changes.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Library"
| where OperationName == "Library.AgentDeleted"
```

---

### Alert Name:  
`Agent Deletion Alert`

### Email Subject:  
`Alert: Agent Deleted in Azure DevOps`

### Email Body:  
```
Hello,

An agent has been removed from the agent pool in your Azure DevOps environment.  
This action could indicate a configuration update or scaling activity.

**Details:**  
- Query: Agent Deleted in Azure DevOps  
- Category: Library  
- Operation(s): Agent Deleted

Please review this deletion in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
