### Query Name:  
`Billing Mode Updated in Azure DevOps`

### Query Description:  
Monitors when the billing mode is updated in Azure DevOps to track changes in subscription settings and ensure proper financial oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Billing"
| where OperationName == "Billing.BillingModeUpdate"
```

---

### Alert Name:  
`Billing Mode Update Alert`

### Email Subject:  
`Alert: Billing Mode Updated in Azure DevOps`

### Email Body:  
```
Hello,

The billing mode has been updated in your Azure DevOps environment.  
This action could indicate a change in subscription settings or financial configurations.

**Details:**  
- Query: Billing Mode Updated in Azure DevOps  
- Category: Billing  
- Operation(s): Billing Mode Update

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
