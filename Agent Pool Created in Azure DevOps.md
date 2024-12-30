### Query Name:  
`Agent Pool Created in Azure DevOps`

### Query Description:  
Monitors when an agent pool is created in Azure DevOps to track infrastructure changes.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Library"
| where OperationName == "Library.AgentPoolCreated"
```

---

### Alert Name:  
`Agent Pool Creation Alert`

### Email Subject:  
`Alert: Agent Pool Created in Azure DevOps`

### Email Body:  
```
Hello,

An agent pool has been created in your Azure DevOps environment.  
This action could indicate a configuration update or a new infrastructure setup.

**Details:**  
- Query: Agent Pool Created in Azure DevOps  
- Category: Library  
- Operation(s): Agent Pool Created

Please review this addition in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
