>[!Warning] On the Exam
> - Standard
> 	- Best-Effort ordering; no rigid preservation of message order
> 	- At-least-once delivery; could be more than one copy of a msg
> - FIFO
> 	- Duplicates are removed with Exactly-Once processing
> 	- Message order is strictly preserved

- FIFO
	- 300 TPS without batching
	- 3000 transations per second with batching
	- Must have ``.fifo` suffix
- Standard
	- Scalable, as wide as required
	- Near unlimited TPS