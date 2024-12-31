# Azure DevOps Monitoring Queries and Alerts

This repository contains a collection of Kusto Query Language (KQL) queries and alert configurations for monitoring various activities in Azure DevOps. Each file in this repository corresponds to a specific event or action in Azure DevOps that is being monitored.

## Directory Structure

The repository is organized as follows, with each file representing an audited event or action:

```
.
├── Agent Addition or Deletion in Azure DevOps.md
├── Agent Pool Creation or Deletion in Azure DevOps.md
├── Billing Mode and Subscription Changes in Azure DevOps.md
├── Extension Operations in Azure DevOps.md
├── Group Operations in Azure DevOps.md
├── Licensing Operations in Azure DevOps.md
├── Modify or Remove Access Control Lists in Azure DevOps.md
├── Modify or Remove Permissions in Azure DevOps.md
├── Organization Operations in Azure DevOps.md
├── Organization Policy Operations in Azure DevOps.md
├── PAT Operations in Azure DevOps.md
├── Pipeline Operations in Azure DevOps.md
├── SSH Key Operations in Azure DevOps.md
├── Service Connection Operations in Azure DevOps.md
```

## Usage

Each file contains the following sections:

- **Query Name**: The name of the query.
- **Query Description**: A brief description of what the query monitors.
- **Query**: The KQL query used to monitor the specific event or action.
- **Alert Name**: The name of the alert.

## Example

Here is an example from the file `SSH Key Operations in Azure DevOps.md`:

```markdown
### Query Name:  
`SSH Key Operations in Azure DevOps`

### Query Description:  
Monitors SSH key operations in Azure DevOps, specifically creation and revocation, to ensure proper oversight of secure access configurations.

### Query:  
```kql
AzureDevOpsAuditing
| where Area == "Token"
| where OperationName == "Token.SshCreateEvent" or OperationName == "Token.SshRevokeEvent"
```

---

### Alert Name:  
`SSH Key Operations Alert`

## License
This project is licensed under the MIT License 