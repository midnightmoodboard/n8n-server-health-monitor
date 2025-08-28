# N8N Server Health Monitor

A comprehensive N8N workflow that monitors server health across multiple services and infrastructure components every 15 minutes, with automatic logging to Notion database.

## Features

- **PostgreSQL Database**: Native connection health checks with active connection counts
- **HTTP Services**: Health endpoint monitoring for Grafana, Ollama AI, Letta AI, Prometheus, N8N
- **Docker Containers**: Container status verification using execute commands  
- **Response Time Tracking**: Performance metrics for each monitored service
- **Notion Integration**: Automatic logging of all health check results with timestamps
- **Error Classification**: Detailed error categorization and troubleshooting information

## Workflow Structure

### Trigger
**Cron Schedule**: Every 15 minutes using `n8n-nodes-base.cron`

### Node Types Used
- **Native Notion Nodes**: For direct API integration when available
- **HTTP Request Nodes**: For custom API calls and external service integration  
- **Code Nodes**: For data processing and transformation
- **Error Handling**: Continue-on-fail enabled for resilient execution

## Installation & Setup

### Prerequisites
- N8N instance with proper credentials configured
- Notion API integration with write permissions
- Required service access (database, webhooks, etc.)

### Configuration Steps

1. **Import Workflow**:
   ```bash
   # Download the workflow file from this repository
   curl -O https://raw.githubusercontent.com/midnightmoodboard/n8n-server-health-monitor/main/server-health-monitor.json
   
   # Import into your N8N instance via the UI or API
   ```

2. **Configure Credentials**:
   - Update all credential references to match your N8N setup
   - Ensure proper API tokens and database IDs are configured
   - Test all connections before enabling the workflow

3. **Activate Workflow**:
   - Enable the workflow in your N8N instance
   - Monitor initial executions for any configuration issues
   - Verify data appears in target systems as expected

## Usage

This workflow operates automatically based on its configured triggers. Monitor execution through:
- N8N execution history
- Target system data verification  
- Error logs and notifications

## Error Handling

Comprehensive error handling includes:
- Continue-on-fail enabled for all critical nodes
- Detailed error logging to Notion database
- Graceful handling of service timeouts and connection issues

## Contributing

Feel free to submit issues and pull requests to improve this workflow.

## License

Open source - adapt for your infrastructure needs.
