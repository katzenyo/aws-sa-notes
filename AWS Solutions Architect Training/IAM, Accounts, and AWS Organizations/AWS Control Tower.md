- Quick and easy setup of multi-account environments
- Orchestrates other AWS services to provide this functionality
	- Uses Organizations, IAM Identity Center, CloudFormation, Config, and more
- Landing Zone - multi-account environment
	- SSO/ID Federation, Centralized logging & auditing
- Guard Rails - detrect/mandate rules/standards across all accounts
- Account Factory - automates and standardizes new account creation
- Dashboard - single page oversight of entire environment

## Landing Zone

- Well-architected multi-account environment - Home Region
- Built with AWS Organizations, AWS Config, CloudFormation
- Security OU - Log Archive & Audit Accounts (CloudTrail & Config Logs)
- Sandbox OU - Test/less rigid security
- Create other OU's and Accounts
- IAM Identity Center - SSO, multiple accounts, ID Federation
- Monitoring and Notifications - CloudWatch and SNS
- End User account provisioning via Service Catalog

## Guard Rails

- Rules for multi-account governance
- Mandatory, Strongly Recommended, and Elective (optional)
- Preventitive: stops you from doing things
	- Enforced or not enabled
	- e.g. allow or deny regions, or disallow bucket policy changes
- Detective: compliance checks (AWS Config Rules), identifies violations
	- Clear, In Violation, or not enabled
	- Detect CloudTrail enabled or EC2 public IPV4

## Account Factory

- Automated Account Provisioning
	- cloud admins or end users (with permissions)
- Guardrails - automatically added
- Account admin give nto named user (IAM Identity Center)
- Self-service AWS account creation
- Account & network standard configuration
- Accounts can be closed or repurposed
- Can be fully integrated with a business SDLC