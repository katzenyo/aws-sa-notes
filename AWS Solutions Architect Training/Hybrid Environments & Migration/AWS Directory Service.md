## Which to use?

- Simple AD
	- Use this by default
- Microsoft AD
	- Apps in AWS that require an actual Microsoft AD DS or you need a trust domain with on prem AD DS
- AD Connector
	- Use when you need a directory without storing any directory info in the cloud
	- Acts as a proxy to on prem Active Directory

## What is a directory?

- Stores objects (users, groups, computers, servers, file shares) with a structure (inverted tree structure)
- Multiple *trees* are grouped into *forests*
- Commonly used in Windows environments (Active Directory)
- Sign in to multiple devices with same creds, allows centralized asset management
- Microsoft Active Directory Domain Services (AD DS)
	- Open source alternative: SAMBA

## What is Directory Service?

- AWS managed version of Active Directory
- Runs inside a VPC
- Implement HA by deploying into multiple AZs
- Some AWS services require a directory
	- Amazon Workspaces
- Can be isolated, integrated with on prem directory, or act as a proxy back to on prem

## Simple AD Mode Architecture

![[Pasted image 20230316143016.png]]

## AWS Managed Microsoft AD Architecture

![[Pasted image 20230316143149.png]]

## AD Connector Architecture

![[Pasted image 20230316144021.png]]

