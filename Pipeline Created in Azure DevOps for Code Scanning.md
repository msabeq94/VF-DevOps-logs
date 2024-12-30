### Query Name:  
`Pipeline Created in Azure DevOps for Code Scanning`

### Query Description:  
Monitors when a pipeline is created in the "Code Scanning" project in Azure DevOps to track changes in automation workflows and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Pipelines"
| where OperationName == "Pipelines.PipelineCreated"
| where ProjectName == "Code Scanning"
```

---

### Alert Name:  
`Pipeline Creation Alert for Code Scanning`

### Email Subject:  
`Alert: Pipeline Created in Code Scanning Project`

### Email Body:  
```
Hello,

A new pipeline has been created in the "Code Scanning" project of your Azure DevOps environment.  
This action could indicate a new automation workflow or configuration update.

**Details:**  
- Query: Pipeline Created in Azure DevOps for Code Scanning  
- Category: Pipelines  
- Operation(s): Pipeline Created

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
