### Query Name:  
`Modify Access Control Lists in Azure DevOps`

### Query Description:  
Monitors when access control lists (ACLs) are modified in Azure DevOps to track changes in permissions and ensure proper security oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Security"
| where OperationName == "Security.ModifyAccessControlLists"
```

---

### Alert Name:  
`Modify Access Control Lists Alert`

### Email Subject:  
`Alert: Access Control Lists Modified in Azure DevOps`

### Email Body:  
```
Hello,

An access control list (ACL) has been modified in your Azure DevOps environment.  
This action could indicate a change in permissions or security configurations.

**Details:**  
- Query: Modify Access Control Lists in Azure DevOps  
- Category: Security  
- Operation(s): Modify Access Control Lists

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
