# Spin Locks

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



