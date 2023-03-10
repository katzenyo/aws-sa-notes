
- Postpones delivery of messages
- Sets a value `DelaySeconds`
- `ReceiveMessage` operation returns nothing
- Message timers allow per-message invisibility, overrides any queue settings
	- Min 0m, max 15m
	- Not supported on FIFO queues