>[!Abstract] The Basics
> - Collects and manages operational data (provides insight)
> - Metrics: AWS products, apps, on-prem systems
> - CloudWatch Logs: AWS products, apps, on-prem
> - CloudWatch Events: AWS services & schedules

## Architecture Overview

![[Pasted image 20221213141412.png]]

### Namespace

- Container for monitoring data
- All AWS data goes into a namespace called AWS/*service name*
- Contain metrics

#### Metrics
- Collection of related data points in a time-ordered structure
	- e.g. CPU usage, network in/out, disk IO
	- Metrics are collected across all services, not for specific servers

#### Dimensions
- Allows to view metrics in the context of specific resources

## Alarms

- Linked to a specific metric
- When criteria are met, enters the alarm state and takes an action/SNS