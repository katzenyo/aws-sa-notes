
>[!Warning] On the Exam
> - Scans EC2 instances, instance OS, and containers
> - Searches for v ulnerabilities and deviations against best practice
> - Network Assessment only (agentless operation)
> - Network & Host assessment together (requires agent)
> - Important packages germane to Inspector:
> 	- Common vulnerabilities and exposures package (CVE)
> 	- Center for Internet Security (CIS) Benchmarks package
> 	- Security best practices for Inspector

- Provides report of findings in order of priority
- Rules packages determine what is checked
- Agent can provide additional OS visibility
- Checks reachability end to end
	- `RecognizedPortWithListener`
	- `RecognizedPortNoListener`
	- `RecognizedPortNoAgent`
	- `UnrecognizedPortWithListener`