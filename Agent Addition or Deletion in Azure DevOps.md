### Query Name:  
`Agent Addition or Deletion in Azure DevOps`

### Query Description:  
Monitors when agents are added or deleted in the agent pool in Azure DevOps to track changes and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Library"
| where OperationName == "Library.AgentAdded" or OperationName == "Library.AgentDeleted"
```

---

### Alert Name:  
`Agent Addition or Deletion Alert`