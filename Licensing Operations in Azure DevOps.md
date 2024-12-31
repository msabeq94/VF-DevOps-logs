### Query Name:  
`Licensing Operations in Azure DevOps`

### Query Description:  
Monitors licensing operations in Azure DevOps, including assigning and removing licenses, and managing group rules (creation, deletion, and modification), to ensure proper oversight of user permissions and roles.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Licensing"
| where OperationName == "Licensing.Assigned" or OperationName == "Licensing.Removed" or OperationName == "Licensing.GroupRuleCreated" or OperationName == "Licensing.GroupRuleDeleted" or OperationName == "Licensing.GroupRuleModified"
```

---

### Alert Name:  
`Licensing Operations Alert`