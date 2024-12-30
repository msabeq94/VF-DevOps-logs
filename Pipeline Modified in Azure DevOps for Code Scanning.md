### Query Name:  
`Pipeline Modified in Azure DevOps for Code Scanning`

### Query Description:  
Monitors when a pipeline is modified in the "Code Scanning" project in Azure DevOps to track changes in automation workflows and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Pipelines"
| where OperationName == "Pipelines.PipelineModified"
| where ProjectName == "Code Scanning"
```

---

### Alert Name:  
`Pipeline Modification Alert for Code Scanning`

### Email Subject:  
`Alert: Pipeline Modified in Code Scanning Project`

### Email Body:  
```
Hello,

A pipeline has been modified in the "Code Scanning" project of your Azure DevOps environment.  
This action could indicate an update to automation workflows or configuration changes.

**Details:**  
- Query: Pipeline Modified in Azure DevOps for Code Scanning  
- Category: Pipelines  
- Operation(s): Pipeline Modified

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
