### Query Name:  
`Agent Pool Creation or Deletion in Azure DevOps`

### Query Description:  
Monitors when agent pools are created or deleted in Azure DevOps to track changes and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Library"
| where OperationName == "Library.AgentPoolCreated" or OperationName == "LibraryAgentPoolDeleted"
```

---

### Alert Name:  
`Agent Pool Creation or Deletion Alert`