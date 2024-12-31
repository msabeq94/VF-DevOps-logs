### Query Name:  
`Service Connection Operations in Azure DevOps`

### Query Description:  
Monitors service connection operations in Azure DevOps, specifically creation, deletion, and modifications, to ensure proper oversight of integrations and access configurations.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Library"
| where OperationName == "Library.ServiceConnectionCreated" or OperationName == "Library.ServiceConnectionDeleted" or OperationName == "Library.ServiceConnectionModified"
```

---

### Alert Name:  
`Service Connection Operations Alert`