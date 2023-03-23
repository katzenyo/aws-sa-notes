
## Streams

- Time ordered list of item changes in a table
- 24-hour rolling window
- Enabled on a per table basis
- Records INSERTS, UPDATES, and DELETES
- Different view types influence what is in the stream

![[Pasted image 20230322170851.png]]

## Triggers

- Item changes generate an event
	- Event contains the data which changed
- An action is taken using that data
- Streams + Lambda is invoked
- Useful for reporting & analytics, aggregation, messaging/notifications

![[Pasted image 20230322171307.png]]