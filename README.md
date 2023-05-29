# OPERATING-SYSTEMS

This Repository contains all the work I have done during the course of learning operating systems

1.) SHELL-IN-C

You need to design a simple shell that can handle three, internal com-
mands – ‘cd’, ‘echo’ and ‘pwd’. These commands would be handled
directly by the shell. Your shell should also be able to handle five exter-
nal commands – ‘ls’, ‘cat’, ‘date’, ‘rm’ and ‘mkdir’. For these
external commands you need to write individual programs to handle these
commands. To handle these external commands, the shell should typically
create a new process, using the fork() system ‘call and within each pro-
cess you need to use the execl() family system call to run the individual
program. The parent program must also wait for the child program to
terminate using the wait() family of system calls.
For each of these commands, you need not handle all the command line
options. Two options per command is sufficient. You need to document
which two options you are handling and need to demonstrate correct func-
tioning of the command with respect to (atleast) your chosen options. You
also need to handle corner cases such as invalid options (graceful degra-
dation).

GITHUB LINK: https://github.com/BudhijaxKuber/Shell-in-C-OS

2.) Thread Scheduling

This exercise is to show you how to use Linux’s scheduling policies for three
threads. You need to launch three threads, each of which relies on three different
functions, countA(), countB() and countC(). Each function does the same
thing, i.e. counts from 1 – 232. The following should be the detailed specification
of each of the threads, to being with:
1. Thread 1 (call it Thr-A()): Uses SCHED OTHER scheduling discipline
with standard priority (nice:0).
2. Thread 2 (call it Thr-B()): Uses SCHED RR scheduling discipline with
default priority.
3. Thread 3 (call it Thr-C()): Uses SCHED FIFO scheduling discipline with
default priority.
Each of these threads must time the process of counting from 1 – 232. You
can use the clock gettime() function for obtaining the actual time ticks that
can be used to compute how long it took to complete a function.
We require you benchmark these three schedulers by changing the scheduling
classes of the three threads (keeping the other scheduling priorities the same),
against the counting program.
For these cases, you would require to rely on pthread schedsetparam() and

related functions for the same. You would require to generate histograms show-
ing which scheduler completes the task when, depending upon the scheduling

policy. You may choose different colors for the histogram bars, with one axis
showing the time to complete, and the other showing the thread priorities. Of
course, you cannot plot for all possible values of priorities; you would require to
choose only some.

GITHUB LINK: https://github.com/BudhijaxKuber/OS-2/blob/main/Q1/q1.1/ans1.1.c

3.) KERNEL MEMORY COPY

This exercise aimed to test your understanding how system calls work. You

need to write a system call, kernel 2d memcpy(), which copies one 2-D float-
ing point matrix to another. You would require using kernel functions like

copy from user() and copy from user() to read data bytes from user space
and write back to user space. In other words, this is a version of memcpy() that
relies on the kernel to do the necessary copy operations, which are otherwise
usually done directly in the user space (using the standard C library routines).

GITHUB LINK: https://github.com/BudhijaxKuber/OS-2/tree/main/Q2

4.) MODIFIED DINING PHILOSOPHER PROBLEM

The dining philosophers problem contains five philosophers sitting on a round
table can perform only one among two actions – eat and think. For eating, each
of them requires two forks, one kept beside each person. Typically, allowing
unrestricted access to the forks may result in a deadlock. (a) Write a program
to simulate the philosophers using threads, and the forks using global variables.
Resolve the deadlock using the following techniques:
1. Strict ordering of resource requests, and
2. Utilization of semaphores to access the resources.
(b) Repeat the above system only using semaphores now with a system that
also has two sauce bowls. The user would require access to one of the two sauce
bowls to eat, and can access any one of them at any point of time.

DRIVE LINK: https://drive.google.com/drive/folders/185CCJ043atRKAHPalpYrnslkvArSARlJ?usp=share_link

5.) INTERPROCESS COMMUNICATION

Write two programs P1 and P2. The first program P1 needs to generate an
array of 50 random strings (of characters) of fixed length each. P1 then sends
a group of five consecutive elements of the array of strings to P2 along with
the ID’s of the strings, where the ID is the index of the array corresponding
to the string. The second program P2 needs to accept the received strings,
and send back the highest ID received back to P1 to acknowledge the strings
received. The program P2 simply prints the ID’s and the strings on the console.
On receiving the acknowledged packet, P1 sends the next five strings, with the
string elements starting from the successor of the acknowledged ID.

The above mechanism needs to be implemented using three different tech-
niques: (i) Unix domain sockets, (ii) FIFOs, and (iii) shared memory. Please

note that you should NOT make assumptions about the reliability of the inter-
process communication mechanism, unless they are guaranteed by the mecha-
nism itself. You should also not use redundant mechanisms to guarantee relia-
bility if the protocol itself guarantees it. Print the amount of time required to

finish receiving the acknowledgment of all 50 strings in the three cases.

DRIVE LINK: https://drive.google.com/drive/folders/1lmwu0Z1ti9wvtHVismbxeCtbbfmH62CX?usp=share_link
