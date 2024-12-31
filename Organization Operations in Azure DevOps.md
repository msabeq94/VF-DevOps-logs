### Query Name:  
`Organization Operations in Azure DevOps`

### Query Description:  
Monitors organization-related operations in Azure DevOps, including creating, deleting, and renaming organizations, to track changes and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Organization"
| where OperationName == "Organization.Create" or OperationName == "Organization.Update.Delete" or OperationName == "Organization.Update.Rename"
```

---

### Alert Name:  
`Organization Operation Alert`