### Query Name:  
`Pipeline Deleted in Azure DevOps for Code Scanning`

### Query Description:  
Monitors when a pipeline is deleted in the "Code Scanning" project in Azure DevOps to track changes in automation workflows and ensure proper oversight.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Pipelines"
| where OperationName == "Pipelines.PipelineDeleted"
| where ProjectName == "Code Scanning"
```

---

### Alert Name:  
`Pipeline Deletion Alert for Code Scanning`

### Email Subject:  
`Alert: Pipeline Deleted in Code Scanning Project`

### Email Body:  
```
Hello,

A pipeline has been deleted in the "Code Scanning" project of your Azure DevOps environment.  
This action could indicate a change in automation workflows or configuration updates.

**Details:**  
- Query: Pipeline Deleted in Azure DevOps for Code Scanning  
- Category: Pipelines  
- Operation(s): Pipeline Deleted

Please review this activity in your Log Analytics Workspace for more information.

Regards,  
Azure Monitoring Team
```
