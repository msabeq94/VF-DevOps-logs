### Query Name:  
`Pipeline Deleted in Azure DevOps for Cloud Services`

### Query Description:  
Monitors when a pipeline is deleted in the "Cloud Services" project in Azure DevOps to track changes in automation workflows and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Pipelines"
| where OperationName == "Pipelines.PipelineDeleted"
| where ProjectName == "Cloud Services"
```

---

### Alert Name:  
`Pipeline Deletion Alert for Cloud Services`

### Email Subject:  
`Alert: Pipeline Deleted in Cloud Services Project`

### Email Body:  
```
Hello,

A pipeline has been deleted in the "Cloud Services" project of your Azure DevOps environment.  
This action could indicate a change in automation workflows or configuration updates.

**Details:**  
- Query: Pipeline Deleted in Azure DevOps for Cloud Services  
- Category: Pipelines  
- Operation(s): Pipeline Deleted

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
