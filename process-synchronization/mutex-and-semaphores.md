# Mutex and Semaphores

**Mutexes** are any kind of lock that provide mutual exclusion. How it is done so depends upon the specific implementation used.

Even Spin Locks with Peterson's solution and atomic hardware locks are mutexes.

Semaphores, are not built to provide mutual exclusion, they may provide so depending upon the implementation.

**Semaphores** are integer variables signifying amount of free resources available, with two operations.

An implementation without spin locks is as follows.

```java
class Semaphore{
    int count; // number of free resources
    Queue<Process> sleepingQueue; // number of waiting processes
    
    Semaphore(int initNumResources){
        count = initNumResources;
        sleepingQueue = new LinkedList<>();
    }
    
    void wait(Process p){
        if(count>0){
            count--;
            allocateResource(p);
        }
        else {
            // make the process wait
            sleepingQueue.offer(p);
        }
    }
    
    void signal(){
        if(sleepingQueue.size()>0){
           Process oldestProcess = q.poll();
           allocateResource(oldestProcess); 
        }
        else {
            count++; // add the resource back
        }
    }
}
```

**Disadvantage -** While we don't have busy waiting, enqueueing and dequeueing involves context switches which has some overhead. Spin locks are better than sleeping queues when the CS is short and not called many times.

A binary semaphore is a sleeping lock used for signalling, with `count = 1`, while a counting semaphore has `count >=1`

Unlike mutexes, semaphores may not provide mutual exclusion. This is because a process that has called `wait()` on the CS may have `signal()` be called by a different process. In mutexes, only the process that acquires the lock may release it.

 

