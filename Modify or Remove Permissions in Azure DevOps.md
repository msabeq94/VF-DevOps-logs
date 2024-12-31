### Query Name:  
`Modify or Remove Permissions in Azure DevOps`

### Query Description:  
Monitors permission operations in Azure DevOps, specifically modifications and removals, to ensure proper oversight of security configurations.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Security"
| where OperationName == "Security.ModifyPermission" or OperationName == "Security.RemovePermission"
```

---

### Alert Name:  
`Permission Operations Alert`