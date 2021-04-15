# Critical Section Problem

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

