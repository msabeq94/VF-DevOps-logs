### Query Name:  
`Pipeline Operations in Azure DevOps for Specific Projects`

### Query Description:  
Monitors pipeline-related operations in Azure DevOps, including creation, deletion, and modifications, specifically for the "Cloud Services," "Code Scanning," and "Public Cloud Resell" projects to ensure proper oversight of automation workflows.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Pipelines"
| where OperationName == "Pipelines.PipelineCreated" or OperationName == "Pipelines.PipelineDeleted" or OperationName == "Pipelines.PipelineModified"
| where ProjectName == "Cloud Services" or ProjectName == "Code Scanning" or ProjectName == "Public Cloud Resell"
```

---

### Alert Name:  
`Pipeline Operations Alert for Specific Projects`