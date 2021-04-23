# Secondary Storage as Virtual Memory

Not all segments/parts of the process have to be loaded into the main memory. We can load the parts in from secondary memory to main memory on demand \(when page fault occurs\)

A **page fault** is when we require a page to be in main memory, but the part of the process for that page is currently in secondary memory.

* **Demand Paging** flow -
  * CPU wants a page that's missing in main memory.
  * Page fault occurs, sends interrupt
  * While process is blocked, page is found in logical address space
  * Translated to physical, page replacement algorithm replaces brings it in to main memory
  * Page table is updated, process resumes

Swapping is the removal of a process \(all it's parts\) from memory to secondary

**Thrashing** is the situation where we bring in too many processes \(degree of multiprogramming high\). 

To stop thrashing - reduce page faults - or look into keeping locality of pages i.e spatially or temporally pages together in memory. CPU will spend all it's time bringing pages in and out, hence CPU utilization will decrease.

An alternative to swapping is page replacement.

* FIFO - can have **Belady's Anomaly** - more page faults with more frames in virtual memory
* Optimal - Needs foresight
* LRU

