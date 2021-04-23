# Contiguous Memory Allocation

**Fixed partitioning** - number of partitions of main memory fixed. We might have **internal fragmentation** - inefficient use of memory as any process, no matter how small, occupies an entire partition. External can also occur.

In **variable partition** scheme, OS keeps track of available blocks of memory and holes.

First fit, best fit and worst fit still suffer from **external fragmentation -** we have enough memory for a process, but not in contiguous spaces. We cannot split a process, so memory cannot be allocated.

**Compaction** attempts to redistribute holes to get rid of external fragmentation.



