### Query Name:  
`SSH Key Operations in Azure DevOps`

### Query Description:  
Monitors SSH key operations in Azure DevOps, specifically creation and revocation, to ensure proper oversight of secure access configurations.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Token"
| where OperationName == "Token.SshCreateEvent" or OperationName == "Token.SshRevokeEvent"
```

---

### Alert Name:  
`SSH Key Operations Alert`