# Lecture 1 Introduction

## 1 Process

==A process is an abstraction corresponding to a running instance of a program.==
Its main role consists in virtualizing the CPU.
A process mainly consists in an execution context, a memory space, a logical state.

## 2 Protection and resource management

==Prevent bad processes from impacting the OS or other processes.==

**Preemption**: give a resource to a process and take it away if needed.==Protection mechanism to prevent a process from monopolizing the CPU==

**Interposition**: place OS between application and resources.(tracks resources, access)

**CPU execution modes**: OS kernel code runs in privileged mode. Application code runs in unprivileged mode.

**System calls**:applications invoke kernel services through the system call mechanism.==Perform things that an application is not allowed to do in unprivileged mode.==

**CPU scheduling**:in charge of deciding which process should run on the CPU.Periodically(for each timer interrupt) and Punctually(in reaction to syscalls and interrupts).

**Context Switch**
1 make decision on the process p2 that should obtain the CPU
2 save execution context of "outgoing" process p1
3 inject/restore the execution context of p2 on the CPU
==between two execution contexts and has *a non-negligible cost*==

**Mode Switch**:==between user and kernel mode in the same execution context==

**Different system contexts**
User-level process context
Kernel process context: running kernel code on behalf of a particular process(e.g. system call)
Kernel code not associated with a process(e.g. timer\device interrupt handler)

**Memory virtualization and protection**
OS must protect the memory space of a process from the actions of other processes

* **Address space** all memory locations that a program can name
* **Virtual space** an address in a process address space
* **Physical space** an address in real memory
* **Address translation**map virtual address to physical address

## 3 Main techniques for virtualization

* **Multiplexing** Exposes a resource among multiple virtual entities
* **Aggregation** Takes multiple resources and makes them appear as a single abstraction.
* **Emulation**Expose (using a level of indirection in software ) a virtual resource that is not provided by the underlying machine. 