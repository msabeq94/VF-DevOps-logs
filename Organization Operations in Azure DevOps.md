### Query Name:  
`Organization Operations in Azure DevOps`

### Query Description:  
Monitors organization-related operations in Azure DevOps, including creating, deleting, renaming organizations, and linking or unlinking them from Azure Active Directory (AAD), to ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Organization"
| where OperationName == "Organization.Create" or OperationName == "Organization.Update.Delete" or OperationName == "Organization.Update.Rename" or OperationName == "Organization.LinkToAAD" or OperationName == "Organization.UnlinkFromAAD"
```

---

### Alert Name:  
`Organization Operations Alert`