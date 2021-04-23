# Address Translation

The CPU can only access two things - its' registers and the main memory.

So every process must be allocated a portion on the limited main memory. Furthermore, we have seen that the memory of processes must be protected from each other.

**Base and limit register** is a simple way of memory separation. A process can only access base to base + limit addresses.

When we write programs, to run the executables must be brought into context of a process. Addresses are converted through address binding.

* The program works with **symbolic** \(logical\) addresses
* The compiler turns it into **relocatable** addresses \(eg. 15 from base\)
* The loader/linker turns it into **absolute** \(physical\) addresses \(eg. 115\)

Compile time binding generates static addresses, while load and execution time generate relocatable.

The mapping is done by the **Memory Management Unit \(MMU\)**

Dynamic Loading or Dynamic Linking \(DLLs\) try to load routines into memory only when they are called, at execution time.

* **Linking** attempts to generate the executables
* **Loading** brings these executables into main memory

