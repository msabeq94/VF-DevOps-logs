### Query Name:  
`Pipeline Modified in Azure DevOps for Public Cloud Resell`

### Query Description:  
Monitors when a pipeline is modified in the "Public Cloud Resell" project in Azure DevOps to track changes in automation workflows and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Pipelines"
| where OperationName == "Pipelines.PipelineModified"
| where ProjectName == "Public Cloud Resell"
```

---

### Alert Name:  
`Pipeline Modification Alert for Public Cloud Resell`

### Email Subject:  
`Alert: Pipeline Modified in Public Cloud Resell Project`

### Email Body:  
```
Hello,

A pipeline has been modified in the "Public Cloud Resell" project of your Azure DevOps environment.  
This action could indicate an update to automation workflows or configuration changes.

**Details:**  
- Query: Pipeline Modified in Azure DevOps for Public Cloud Resell  
- Category: Pipelines  
- Operation(s): Pipeline Modified

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
