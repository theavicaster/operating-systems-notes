# Zombie and Orphan Process

Zombie processes are those where

* The process has finished executing, has itself been removed from process table
* Parent process still has it as it's child in process table \(table limited in space\)

A child process on exiting is always a zombie process till the parent reaps it and removes it from process table.

  
Orphans are processes with terminated parents \(but themselves still execute\)

**Reparenting** is the process of finding a new process for an orphan.

