
- Health checks are separate from but used by records
- Health checkers are located globally
- Health checkers check every 30s (every 10s costs extra)
- TCP, HTTP/HTTPS, HTTP/HTTPS with String Matching
- Two states: health or unhealthy
	- If 18%+ of health checkers report healthy, the health check is considered healthy
	- Unhealthy records are not returned in queries (most of the time)
- Endpoint, CloudWatch Alarm, and Checks of Checks (Calculated)
