# Critical Section and Spin Locks

A typical process follows this stucture 

```java
while(true){
    entry_section
    CRITICAL_SECTION
    exit_section
    remainder_section
}
```

A **race condition** is when concurrent access to shared data gives unexpected output to the data.

Solutions to critical section problem must have following attributes

* **Mutual Exclusion** - One process in CS at a time
* **Progress and Bounded Waiting** - Processes must not wait indefinitely to enter CS

```java
class Lock{
    boolean held
    Lock(){
        held = false;
    }
}

void acquire(Lock lock) {
    while(lock.held == true){
        // spinning while loop
    }

    lock.held = true;
}

void release(Lock lock) {
    lock.held = false;
}
```

If process P1 and P2 call `acquire()` at the same time, mutual exclusion violated as two processes get access to the CS.

This can be solved with Peterson's solution, a modification with -

* Two lock variables
* Turn taking approach

Disadvantages -

* Spin locks waste CPU cycles - **Busy Waiting**
* Needs to know number of processes \(for turns and flags\)



