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
   git clone https://github.com/yati1002/Workflowadvisor.git
   cd Workflowadvisor
   ```

2. **Import the Dashboard Template:**
   - Navigate to your Databricks workspace.
   - Go to the `SQL` section of the nav bar and select `Dashboards`.
   - Click **Create dashboard** dropdown → **Import dashboard from a file**.
   - Select the provided `Workflow Advisor Dashboard.lvdash.json` dashboard template file from this repository.

3. **Configure Data Sources:**
   - Ensure your system tables are correctly set up with the following schemas enabled:
     - `lakeflow`
     - `billing`
     - `compute`
   - Update dataset queries to match your workspace IDs, schemas, and desired filters.

# Databricks Workflow Advisor Dashboard Guide

## Job Cost Summary Tab

### Step 1: Select Filter Inputs
By default, the following filters are applied:
- All job run states
- All job names and owners
- Top 10 jobs in visualizations
- Job start date set to 30 days ago; end date set to today
- All DBR versions and key value tags

**All defaults can be adjusted to fit specific needs.**

### Step 2: View and Analyze Charts

#### Section 1: Job Cost Metrics
- **Counter Charts:** Display aggregate metrics like:
  - Total Job Cost
  - Total Job Runs
  - WorkspaceID counts
  - Runs succeeded/errored/failed/timed out/cancelled

- **Roll-up Visualizations:**
  - **Total Cost Per WorkspaceId:** Identify the most expensive workspace
  - **Daily Cost Per SKU:** Track cost-heavy SKUs (e.g., `ENTERPRISE_JOBS_COMPUTE`)
  - **Top Cost Per Job Owner:** Identify costly jobs by owner
  - **Top Cost Per Job Name:** Identify costly jobs by name
  - **Top Cost Per DBR Version:** Monitor costs associated with DBR upgrades

#### Section 2: Daily Job Run KPIs
- **Daily Runs by WorkspaceId:** Spot costly workspaces
- **Daily Runs by Resulting State:** Investigate high error days
- **Daily Runs by Cluster Source:** Mitigate inefficient clusters (e.g., `ALL PURPOSE CLUSTER`)

#### Section 3: Latest Job Runs Table
This table provides:
- Latest Run Date
- Latest Result State
- Duration of Last Run
- Failure Rate
- % Change in duration compared to previous run

---

## Job Run Metrics Tab

### Step 1: Select Filter Inputs
By default, the following filters are applied:
- **Section 1:** Top 10 jobs in visualizations, last 7 days of data
- **Section 2:** All job names, owners, and run IDs

**All defaults can be adjusted to fit specific needs.**

### Step 2: View and Analyze Charts

#### Section 1: Top Over and Under Provisioned Jobs
- **Least Average CPU:** Identify underutilized jobs
- **Most Average CPU:** Identify jobs maximizing hardware
- **Least Average Memory:** Consider reducing memory allocation
- **Most Average Memory:** Consider increasing memory allocation

#### Section 2: CPU, Memory, and Network Visuals
- **CPU Utilization Per Run**
- **Memory Utilization Per Run**
- **Daily Network Utilization**

All visualizations are interactive and support cross-filtering.

#### Section 3: Granular Job Run Metrics Table
This table provides:
- Run start and end times
- Trigger type
- Termination code
- Cluster ID
- Driver Type
- Worker Node Type and Count
- Avg Memory/CPU Utilization

## Interactive Investigation
Both tabs support interactive filtering via selections in visualizations or top-level filters to provide deeper insights.

## Contribution
We welcome contributions! Feel free to open issues or submit pull requests for improvements or bug fixes.

## Authors
- **Yatish Anand** - Sr. Solutions Architect @ Databricks
- **Bo Cheng** - Solutions Architect @ Databricks

## License
This project is licensed under the [DB License](LICENSE.md).

## Support
For questions or feedback, please reach out via the GitHub Issues tab or contact your Databricks account team.