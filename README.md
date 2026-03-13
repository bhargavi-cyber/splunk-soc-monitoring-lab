# Splunk SOC Monitoring Lab

This project demonstrates how Splunk can be used to monitor log data,
detect failures, and generate alerts using SPL queries.

The project includes:

- Data exploration using SPL
- Failure detection analysis
- Dashboard visualizations
- Automated alert configuration

## Splunk Architecture

The lab demonstrates the core Splunk architecture components:

- Forwarder
- Indexer
- Search Head
- Buckets (Hot, Warm, Cold)

Documentation is available in:

docs/splunk-architecture.md

## SPL Queries

Key SPL queries used in this project:

- Data exploration
- Failure detection
- Partner failure analysis
- Host activity monitoring
- Success rate monitoring

Queries are available in the `queries/` directory.

## Monitoring Dashboard

A dashboard was created to visualize system activity.

Panels include:

- Failures by User
- Total Calls by Host
- Total Network Failures
- Failures by Partner

<img src="screenshots/04-dashboard-overview.png" width="700">

## Alert Configuration

An alert was configured to detect when call success rate drops below threshold.

Alert details:

- Runs every hour
- Trigger condition: success rate below threshold
- Action: Add to triggered alerts

<img src="screenshots/06-alert-creation.png" width="700">

## Repository Structure

splunk-soc-monitoring-lab
├── docs
├── project
├── queries
├── screenshots
└── README.md

## Skills Demonstrated

- Splunk log analysis
- SPL query writing
- Dashboard creation
- Alert configuration
- Data visualization
