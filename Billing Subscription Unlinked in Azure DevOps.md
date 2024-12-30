### Query Name:  
`Billing Subscription Unlinked in Azure DevOps`

### Query Description:  
Monitors when a subscription is unlinked from billing in Azure DevOps to track changes in financial configurations and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Billing"
| where OperationName == "Billing.SubscriptionUnlink"
```

---

### Alert Name:  
`Billing Subscription Unlink Alert`

### Email Subject:  
`Alert: Subscription Unlinked from Billing in Azure DevOps`

### Email Body:  
```
Hello,

A subscription has been unlinked from billing in your Azure DevOps environment.  
This action could indicate a change in financial configurations or subscription updates.

**Details:**  
- Query: Billing Subscription Unlinked in Azure DevOps  
- Category: Billing  
- Operation(s): Subscription Unlink

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
