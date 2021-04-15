# Deadlock

Situation where a set of processes are blocked as each process is holding a resource. Each process  is waiting for another resource acquired by some other process.

**Necessary conditions -**

* Mutual Exclusion
* Hold and Wait
* No Preemption
* Circular Wait - A set {T0 , T1 , ..., Tn } of waiting threads must exist such that T0 is waiting for a resource held by T1 , T1 is waiting for a resource held by T2 , ..., Tn−1 is waiting for a resource held by Tn , and Tn is waiting for a resource held by T0.

Handling deadlock -

* **Prevention -** 
* Violate the necessary conditions

  * Mutual exclusion can't be helped
  * Allocate all the resources first. Then start the process execution. Can have starvation where processes keep waiting for resources.
  * Allow high priority process to preempt lower
  * Give each process an identifier and keep an ordering by letting processes take resources in ascending order. Eg. P1 gets R5. That means P1 can't get R1 to R4 anymore. Can get R6+.

* **Avoidance -**
*  Banker's Algorithm has prior information about below and makes sure processes are always in their bounds in a safe state

  * Max need of each process
  * Current allocation of resources
  * Max free resources

* **Detection and Recovery -**

  * Detection checks for cycle in RAG if there's single instances of each resource. Otherwise cannot be done.
  * Recovery kills process or preempts resources

* **Ignore and reboot when stuck -** 
  * Windows follows this. Works as deadlocks are rare.

