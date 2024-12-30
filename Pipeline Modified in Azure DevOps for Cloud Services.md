### Query Name:  
`Pipeline Modified in Azure DevOps for Cloud Services`

### Query Description:  
Monitors when a pipeline is modified in the "Cloud Services" project in Azure DevOps to track changes in automation workflows and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Pipelines"
| where OperationName == "Pipelines.PipelineModified"
| where ProjectName == "Cloud Services"
```

---

### Alert Name:  
`Pipeline Modification Alert for Cloud Services`

### Email Subject:  
`Alert: Pipeline Modified in Cloud Services Project`

### Email Body:  
```
Hello,

A pipeline has been modified in the "Cloud Services" project of your Azure DevOps environment.  
This action could indicate an update to automation workflows or configuration changes.

**Details:**  
- Query: Pipeline Modified in Azure DevOps for Cloud Services  
- Category: Pipelines  
- Operation(s): Pipeline Modified

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
