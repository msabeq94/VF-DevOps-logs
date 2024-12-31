### Query Name:  
`Extension Operations in Azure DevOps`

### Query Description:  
Monitors key extension-related actions in Azure DevOps, such as enabling, disabling, installing, uninstalling, or updating extensions, to track changes in functionality.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Extension"
| where OperationName == "Extension.Disabled" or OperationName == "Extension.Enabled" or OperationName == "Extension.Installed" or OperationName == "Extension.Uninstalled" or OperationName == "Extension.VersionUpdated"
```

---

### Alert Name:  
`Extension Operation Alert`