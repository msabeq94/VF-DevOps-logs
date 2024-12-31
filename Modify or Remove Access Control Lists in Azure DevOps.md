### Query Name:  
`Modify or Remove Access Control Lists in Azure DevOps`

### Query Description:  
Monitors access control list (ACL) operations in Azure DevOps, specifically modifications and removals, to ensure proper oversight of security configurations.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Security"
| where OperationName == "Security.ModifyAccessControlLists" or OperationName == "Security.RemoveAccessControlLists"
```

---

### Alert Name:  
`Access Control List Operations Alert`