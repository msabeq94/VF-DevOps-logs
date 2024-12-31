### Query Name:  
`Organization Policy Operations in Azure DevOps`

### Query Description:  
Monitors policy-related operations at the organization level in Azure DevOps, including adding, removing, and updating enforced policies, to ensure compliance and oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "OrganizationPolicy"
| where OperationName == "OrganizationPolicy.EnforcePolicyAdded" or OperationName == "OrganizationPolicy.EnforcePolicyRemoved" or OperationName == "OrganizationPolicy.PolicyValueUpdated"
```

---

### Alert Name:  
`Organization Policy Operations Alert`