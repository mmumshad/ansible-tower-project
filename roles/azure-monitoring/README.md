# Ansible Role: azure-boot-diagnostics

Note: This was not enabled by default

**Research:** The Azure Log Analytics (OMS) agent, previously referred to as the Microsoft Monitoring Agent (MMA) or OMS Linux agent, was developed for comprehensive management across on-premises machines, computers monitored by System Center Operations Manager, and virtual machines in any cloud.

Reference: https://docs.microsoft.com/en-us/azure/azure-monitor/platform/log-analytics-agent

Log Analytics virtual machine extension for Linux
https://docs.microsoft.com/en-us/azure/virtual-machines/extensions/oms-linux

Using Log Analytics VM Extension to enable monitoring of VM

**Required Inputs**:
 - *log_analytics_workspace_id:* Log Analytics Workspace ID
 - *log_analytics_workspace_Key:* Log Analytics Workspace Key
