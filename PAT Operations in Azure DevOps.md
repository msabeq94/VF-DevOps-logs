### Query Name:  
`Personal Access Token Operations in Azure DevOps`

### Query Description:  
Monitors Personal Access Token (PAT) operations in Azure DevOps, including creation, expiration, public discovery, revocation, and updates, to ensure proper security oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Token"
| where OperationName == "Token.PatCreateEvent" or OperationName == "Token.PatExpiredEvent" or OperationName == "Token.PatPublicDiscoveryEvent" or OperationName == "Token.PatRevokeEvent" or OperationName == "Token.PatUpdateEvent"
```

---

### Alert Name:  
`PAT Operations Alert`