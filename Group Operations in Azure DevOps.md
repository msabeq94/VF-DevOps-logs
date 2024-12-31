### Query Name:  
`Group Operations in Azure DevOps`

### Query Description:  
Monitors group-related operations in Azure DevOps, including group creation, deletion, and membership updates, to track changes in team structures and permissions.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Group"
| where OperationName == "Group.CreateGroups" or OperationName == "Group.UpdateGroups.Delete" or OperationName == "Group.UpdateGroupMembership.Add" or OperationName == "Group.UpdateGroupMembership.Remove"
```

---

### Alert Name:  
`Group Operation Alert`