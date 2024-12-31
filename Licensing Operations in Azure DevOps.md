### Query Name:  
`Licensing Operations in Azure DevOps`

### Query Description:  
Monitors licensing-related operations in Azure DevOps, including assigning and removing licenses, to track changes in user permissions and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Licensing"
| where OperationName == "Licensing.Assigned" or OperationName == "Licensing.Removed"
```

---

### Alert Name:  
`Licensing Operation Alert`