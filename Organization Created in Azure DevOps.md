### Query Name:  
`Organization Created in Azure DevOps`

### Query Description:  
Monitors when a new Azure DevOps organization is created to track provisioning and ensure compliance.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Organization"
| where OperationName == "Organization.Create"
```

---

### Alert Name:  
`Organization Creation Alert`

### Email Subject:  
`Alert: Organization Created in Azure DevOps`

### Email Body:  
```
Hello,

A new Azure DevOps organization has been created.  
This action could indicate a provisioning activity or a new project setup.

**Details:**  
- Query: Organization Created in Azure DevOps  
- Category: Organization  
- Operation(s): Organization Created

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
