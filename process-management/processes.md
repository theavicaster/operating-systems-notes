# Processes

A process is an instance of a program in execution.

It is the execution environment for a program, essentially one or more threads + address space

* Threads - for concurrency
* Memory - 
  * Shared between threads. 
  * Address space of each process is protected from others

Every process has it's own context \(in the PCB or **Process Control Block**\), which contains among others,

* Process ID
* Parent Process ID
* Process State \( Ready, Running, Waiting\)
* Process Priority
* Program Counter - Address of next executable instruction
* State of CPU registers \(in case of interrupts or context switches\)



