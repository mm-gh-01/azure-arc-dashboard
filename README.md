# Adaptive Cloud Situational Awareness Dashboard

Welcome to the Adaptive Cloud Situational Awareness Dashboard repository. This project aims to provide a ready to try PowerBI dashboard for a consolidated view of your Azure-native and Arc-enabled operating systems (Windows and Linux) and SQL databases (IaaS and PaaS) estate. 

The dashboard consists of a single PowerBI template file (ArcDashboard.pbit) and an auxiliary metadata enrichment Excel file (ProductLifecycle.xlsx). The data is retrieved using the built-in PowerBI Azure Resource Graph connector and three KQL queries. 

## Features

- Real-time monitoring of cloud resources
- Customizable alerts and notifications
- Detailed analytics and reporting
- Integration with various cloud providers

## What's new

### March 12, 2025
- Added telemetry and new report for Arc-enabled SQL Migration Assessment (preview) results
- Updated various SQL reports with migration assessment enablement or readiness status
- Updated the "Lifecycle Horizons" report graphs dates and visual styling

## Prerequisites

- PowerBI Desktop installed locally ([Download Microsoft Power BI Desktop from Official Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=58494))
- Azure RBAC read permissions on the following resource types:
    - Microsoft.HybridCompute/machines
    - Microsoft.Compute/virtualmachines
    - Microsoft.AzureArcData/sqlserverinstances
    - Microsoft.AzureArcData/sqlserverinstances/databases
    - Microsoft.Sql/servers
    - Microsoft.Sql/servers/databases
    - Microsoft.Sql/managedinstances
    - Microsoft.Sql/managedInstances/databases
    - Microsoft.SqlVirtualMachine/sqlVirtualMachines

## Known issues
None for the last release.

## Installation

1. Dowload ArcDashboard.pbit and ProductLifecycle.xlsx and save to local folder C:\ArcDashboard.
> [!NOTE]
> If saving to a different folder path, follow the instructions further down to modify the PowerBI report data source path for ProductLifecycle.xlsx

2. Open the file ArcDashboard.pbit. Wait for PowerBI Desktop to load and begin refreshing data. When the authentication prompt pops up, click **Sign in**. Follow one of the two procedures below, depending on whether you are authenticating to the current or alternative Entra ID tenant.

    <details>
        <summary>Authenticate with the user's current credentials and Entra ID tenant</summary>
            1. In the authentication prompt, click on your logged in account<br/>
            2. After the authentication process completes, click "Connect"
    </details>
    <details>
        <summary>Authenticate with alternate credentials/Entra ID tenant</summary>
            1. In the authentication prompt, click on "Use another account"<br/>
            2. Click "Sign-in options"<br/>
            3. Click "Sign in to an organization"<br/>
            4. Type in the Entra ID tenant domain name and click "Next"<br/>
            5. Click "Use another account", enter your credentials and complete the authentication process<br/>
            6. After the authentication process completes, click "Connect"
    </details>

3. The datasets should start refreshing now. Depending on the number of Azure virtual machines, Azure SQL Database, Azure SQL Managed Instance, and Arc-managed servers, this might take a while.<br/>
4. When completed, the dashboard visuals will refresh with your environment data.<br/>
5. Finally, save the report as a PowerBI .pbix file. The query results data is persisted in the file so you can share with others who do not have direct Azure permissions to refresh the data.
