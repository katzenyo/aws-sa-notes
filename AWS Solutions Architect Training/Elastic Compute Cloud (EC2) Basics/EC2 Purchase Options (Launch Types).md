>[!Warning] On the Exam
> - Focus on [[EC2 Purchase Options (Launch Types)#On-Demand|On-Demand]], [[EC2 Purchase Options (Launch Types)#Reserved|Reserved]], and [[EC2 Purchase Options (Launch Types)#Spot Pricing|Spot]] instances

## On-Demand Instances

>[!Warning] On the Exam
> - Ideal for:
> 	- Short term workloads
> 	- Unknown workloads
> 	- Apps which can't be interrupted

- Default
	- Start with this unless you can justify using other options
- Isolated
	- Multiple customer instances run on same shared host
- Instances of different sizes run on same EC2 hosts
	- Consume a defined allocation of resources from a host
- Per-second billing
	- Consumed while instance is running
	- Dependant resources (storage) consume capacity and are billed even if the instance is not running
- Benefits:
	- No interruption
	- No capacity reservation
	- Predictable pricing
	- No upfront cost
	- No discount

## Spot Pricing

>[!Warning] On the Exam
> - Ideal for:
> 	- Non-time critical
> 	- Anything that can be rerun
> 	- Bursty capacity needs
> 	- Cost sensitive workloads
> 	- Anything stateless

- AWS selling unused EC2 host capacity for up to 90% discount
	- Spot price is based on the spare capacity at any given time
- Don't use for:
	- Workloads that can't tolerate interruptions
	- No long-term use cases

## Reserved Instances

>[!Warning] On the Exam
> - Ideal for:
>	- Infrastructure which have known usage
>	- Consistent access/usage
>	- Can't tolerate interruption

- Long-term commitments for EC2 consumption
- No reservation
	- Full per second price
- Matching instance
	- Reduced or no per second cost
- Unused reservation
	- Still billed regardless of usage
- Partial coverage of larger instance
- Reservation terms
	- 1 year or 3 year terms
	- Pay up front for the entire term
	- No-upfront
		- Some savings for agreeing to the term
		- Per second fee
	- All upfront
		- No per second fee
	- Partial upfront
		- Smaller lump sum in advance
		- Reduced per/s fee

### Scheduled Reserved

- Ideal for:
	- Long-term usage that doesn't run constantly
	- Daily tasks (batch processing)
	- Weekly tasks (data analysis, sales analysis, etc)
	- Scheduling a set # of hours per month
- Restrictions:
	- Doesn't support all instance types or regions
	- 1200 hours minimum per year + 1 year term commitments

### Capacity Reservations

- Regional reservation
	- Provides a billing discount for valid instances launched in any AZ in the region
	- Doesn't reserve capacity within an AZ
		- Risky during major faults where capacity is limited
- Zonal Reservations
	- Apply to a single AZ
		- Provides billing discounts and capacity reservation in that single AZ
- Both regional & zonal reservations require a 1 or 3 year commitment reservation
- On-demand capacity reservations
	- Ensure you always have access to capacity in an AZ when necessary
	- No term limits
	- Subject to full on-demand pricing
		- Pay regardless of whether you consume capacity or not

### Savings Plan

> [!Warning] On the Exam
> - Allows a business migrating from EC2 to serverless to gain cost-effective access to using Fargate, Lambda, etc

- Hourly commitment for a 1 or 3 year term
- Two main types
	- General compute $ amounts
		- Save up to 66% of on-demand versions
	- Specific EC2 savings plan
		- Flexibility on size & OS
		- Up to 72% savings
- Supports [[EC2 Basics|EC2]], Fargate, and Lambda
	- Products have normal on-demand rate and a savings plan rate
	- Savings plan rate
		- Resource usage consumes savings plan commitment at the reduced savings plan rate
	- If you go beyond your commitment, [[EC2 Purchase Options (Launch Types)#On-Demand Instances|on-demand]] pricing is used


## Dedicated Hosts

- EC2 host dedicated entirely to you
	- Come with all resources from having a physical machine
- No instance charges
- Ideal for:
	- Licensing based on sockets/cores of physical machine
- Host Affinity
	- Links certain instances to EC2 hosts

## Dedicated Instances

- Dedicated instances on a host
	- Host is not shared by other EC2 customer instances
- Extra charges for instances but you receive dedicated hardware
- Billed for:
	- One-off hourly fee for regions where Dedicated Instances are used
	- Fee for the instances themselves
- Ideal for:
	- For infrastructure that has strict requirements that systems can't be shared with others
	- Requirements to not share hardware but don't want to manage the hardware/host itself