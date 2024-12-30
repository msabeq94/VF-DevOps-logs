### Query Name:  
`Billing Subscription Linked in Azure DevOps`

### Query Description:  
Monitors when a subscription is linked to billing in Azure DevOps to track changes in financial configurations and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Billing"
| where OperationName == "Billing.SubscriptionLink"
```

---

### Alert Name:  
`Billing Subscription Link Alert`

### Email Subject:  
`Alert: Subscription Linked to Billing in Azure DevOps`

### Email Body:  
```
Hello,

A subscription has been linked to billing in your Azure DevOps environment.  
This action could indicate a new financial configuration or subscription update.

**Details:**  
- Query: Billing Subscription Linked in Azure DevOps  
- Category: Billing  
- Operation(s): Subscription Link

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
