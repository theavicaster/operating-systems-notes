# Priority Inversion

This is a problem in semaphores, related to **Bounded Waiting**

* Suppose there are 3 processes with priorities H,M,L
* H and L both work on a **Critical Section** which needs **atomic** access. M doesn't.
* Sequence is as follows -
  * L is running and scheduled
  * H is ready to run. Waits for L to finish before being scheduled.
  * This is because H would change state of CS and ruin the progress of L.
  * M is ready to run. Preempts L. M is now running.
  * M finishes. L comes back. L finishes.
  * Finally H is scheduled and runs.
* The issue is that H was waiting for lower priority M which doesn't work on the same CS.
* Solution is called **priority inheritance.**
* At the moment H waits for L, L's priority becomes equal to H.
* Hence M cannot preempt it.



