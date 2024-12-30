# Azure DevOps Monitoring Queries and Alerts

This repository contains a collection of Kusto Query Language (KQL) queries and alert configurations for monitoring various activities in Azure DevOps. Each file in this repository corresponds to a specific event or action in Azure DevOps that is being monitored.

## Directory Structure

The repository is organized as follows:

```
.
├── Agent Added in Azure DevOps.md
├── Agent Deleted in Azure DevOps.md
├── Agent Pool Created in Azure DevOps.md
├── Agent Pool Deleted in Azure DevOps.md
├── Billing Mode Updated in Azure DevOps.md
├── Billing Subscription Linked in Azure DevOps.md
├── Billing Subscription Unlinked in Azure DevOps.md
├── Extension Disabled in Azure DevOps.md
├── Extension Enabled in Azure DevOps.md
├── Extension Installed in Azure DevOps.md
├── Extension Uninstalled in Azure DevOps.md
├── Extension Version Updated in Azure DevOps.md
├── Group Created in Azure DevOps.md
├── Group Deleted in Azure DevOps.md
├── Group Membership Changes in Azure DevOps.md
├── Group Rule Created in Azure DevOps.md
├── Group Rule Deleted in Azure DevOps.md
├── Group Rule Modified in Azure DevOps.md
├── Licensing Assigned in Azure DevOps.md
├── Licensing Removed in Azure DevOps.md
├── Modify Access Control Lists in Azure DevOps.md
├── Modify Permissions in Azure DevOps.md
├── Organization Created in Azure DevOps.md
├── Organization Deleted in Azure DevOps.md
├── Organization Renamed in Azure DevOps.md
├── Personal Access Token Created in Azure DevOps.md
├── Personal Access Token Expired in Azure DevOps.md
├── Personal Access Token Public Discovery in Azure DevOps.md
├── Personal Access Token Revoked in Azure DevOps.md
├── Personal Access Token Updated in Azure DevOps.md
├── Pipeline Created in Azure DevOps for Cloud Services.md
├── Pipeline Created in Azure DevOps for Code Scanning.md
├── Pipeline Created in Azure DevOps for Public Cloud Resell.md
├── Pipeline Deleted in Azure DevOps for Cloud Services.md
├── Pipeline Deleted in Azure DevOps for Code Scanning.md
├── Pipeline Deleted in Azure DevOps for Public Cloud Resell.md
├── Pipeline Modified in Azure DevOps for Cloud Services.md
├── Pipeline Modified in Azure DevOps for Code Scanning.md
├── Pipeline Modified in Azure DevOps for Public Cloud Resell.md
├── Remove Access Control Lists in Azure DevOps.md
├── Remove Permission in Azure DevOps.md
├── SSH Key Created in Azure DevOps.md
├── SSH Key Revoked in Azure DevOps.md
├── Service Connection Created in Azure DevOps.md
├── Service Connection Deleted in Azure DevOps.md
├── Service Connection Modified in Azure DevOps.md
```

## Usage

Each file contains the following sections:

- **Query Name**: The name of the query.
- **Query Description**: A brief description of what the query monitors.
- **Query**: The KQL query used to monitor the specific event or action.
- **Alert Name**: The name of the alert.
- **Email Subject**: The subject line for the alert email.
- **Email Body**: The body content for the alert email.

## Example

Here is an example from the file `Pipeline Deleted in Azure DevOps for Cloud Services.md`:

```markdown
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
Azure Monitoring Team
```
### License

This project is licensed under the MIT License .