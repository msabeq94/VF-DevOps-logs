### Query Name:  
`Pipeline Created in Azure DevOps for Cloud Services`

### Query Description:  
Monitors when a pipeline is created in the "Cloud Services" project in Azure DevOps to track changes in automation workflows and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Pipelines"
| where OperationName == "Pipelines.PipelineCreated"
| where ProjectName == "Cloud Services"
```

---

### Alert Name:  
`Pipeline Creation Alert for Cloud Services`

### Email Subject:  
`Alert: Pipeline Created in Cloud Services Project`

### Email Body:  
```
Hello,

A new pipeline has been created in the "Cloud Services" project of your Azure DevOps environment.  
This action could indicate a new automation workflow or configuration update.

**Details:**  
- Query: Pipeline Created in Azure DevOps for Cloud Services  
- Category: Pipelines  
- Operation(s): Pipeline Created

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Vodafone Azure DevOps Team
```
