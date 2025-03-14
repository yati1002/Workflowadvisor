# Databricks Workflow Advisor Dashboard

## Introduction
The **Databricks Workflow Advisor Dashboard** is designed to help Databricks customers monitor and optimize workflow cost and utilization. This AI/BI dashboard template leverages system tables to provide insights into job performance, helping users identify under- or over-provisioned compute resources for efficient cost management.

### Key Features
- **Aggregated Job Summary Metrics:**
  - Total job cost, total job runs, average run duration
- **Cost Attribution:**
  - SKU, job owner, workspace ID, job name, and DBR version
- **Job Run Insights:**
  - Identify job runs by resulting state, workspace ID, and cluster source
- **Utilization Metrics:**
  - CPU, memory, and data network send insights
- **Top Job Analysis:**
  - Identify the top jobs that are under- or over-provisioned for optimization

## Getting Started
Follow these steps to deploy the **Databricks Workflow Advisor Dashboard** in your workspace.

### Prerequisites
- A Databricks workspace with system tables enabled
- Access to the [Dashboard Template on GitHub](#)
- Appropriate permissions to import dashboards and run queries

## Installation
1. **Clone the Repository:**
   ```bash
   git clone <repo-url>
   cd databricks-workflow-advisor-dashboard
   ```

2. **Import the Dashboard Template:**
   - Navigate to your Databricks workspace.
   - Go to the `SQL` workspace.
   - Click **Dashboards** → **Import**.
   - Select the provided `.json` dashboard template file from this repository.

3. **Configure Data Sources:**
   - Ensure your system tables are correctly set up.
   - Update dataset queries to match your workspace IDs, schemas, and desired filters.

## Using the Dashboard
### Job Cost Summary Tab

**Step 1:** Select Filter Inputs
- Default filters include:
  - All resulting states of job runs
  - All job names
  - All job owners
  - Top 10 jobs displayed in visualizations
  - Job start date = 30 days ago
  - Job end date = today
  - All DBR versions
  - All key-value tags

**Step 2:** Analyze Visualizations
- Explore cost breakdowns, utilization metrics, and top job insights.
- Identify opportunities to optimize under- or over-provisioned jobs.

## Contribution
We welcome contributions! Feel free to open issues or submit pull requests for improvements or bug fixes.

## Authors
- **Yatish Anand** - Sr. Solutions Architect @ Databricks
- **Bo Cheng** - Solutions Architect @ Databricks

## License
This project is licensed under the [DB License](LICENSE.md).

## Support
For questions or feedback, please reach out via the GitHub Issues tab or contact your Databricks representative.