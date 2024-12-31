### Query Name:  
`Billing Mode and Subscription Changes in Azure DevOps`

### Query Description:  
Tracks significant billing-related actions in Azure DevOps, such as updates to billing modes, linking, or unlinking of subscriptions, to ensure financial configurations are monitored.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Billing"
| where OperationName == "Billing.BillingModeUpdate" or OperationName == "Billing.SubscriptionLink" or OperationName == "Billing.SubscriptionUnlink"
```

---

### Alert Name:  
`Billing Mode or Subscription Change Alert`