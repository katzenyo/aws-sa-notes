- Running more than one OS on a piece of hardware
- Kernel runs in privileged mode
	- only part that can direclty interact with hardware
- Applications (user mode/unprivileged mode)
- Software virtualization (hypervisor)
	- Binary Translation: intercepts privileged operations
- Para-virtualization: works on a subset of OS, makes hypercalls
	- OS calls the hypervisor, not the hardware
- SR-IOV

## Hardware Assisted Virtualization

- Hardware is virtualization-aware
- CPU is aware of the virtualization
	- CPU intercepts privileged operations by guest OS

## Enhanced Networking

- Network performance is improved 
- Nitro hypervisor stack