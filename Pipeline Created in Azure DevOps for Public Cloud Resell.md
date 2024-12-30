### Query Name:  
`Pipeline Created in Azure DevOps for Public Cloud Resell`

### Query Description:  
Monitors when a pipeline is created in the "Public Cloud Resell" project in Azure DevOps to track changes in automation workflows and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Pipelines"
| where OperationName == "Pipelines.PipelineCreated"
| where ProjectName == "Public Cloud Resell"
```

---

### Alert Name:  
`Pipeline Creation Alert for Public Cloud Resell`

### Email Subject:  
`Alert: Pipeline Created in Public Cloud Resell Project`

### Email Body:  
```
Hello,

A new pipeline has been created in the "Public Cloud Resell" project of your Azure DevOps environment.  
This action could indicate a new automation workflow or configuration update.

**Details:**  
- Query: Pipeline Created in Azure DevOps for Public Cloud Resell  
- Category: Pipelines  
- Operation(s): Pipeline Created

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
