# Executing malicious code with buffer overflows

![Call Stack](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d3/Call_stack_layout.svg/342px-Call_stack_layout.svg.png)

Whenever you call a function, you add a "stack frame" onto the stack memory
which contains information about the function's local variables, its parameters,
and more importantly its return address.

Programs have something called an "instruction pointer" which points to the area
in memory the current instruction being executed is located.

Whenever a function returns, the stack frame is popped off the call stack and
the instruction pointer is set to the return address.

If we were somehow able to somehow overwrite this return address, it could be
possible for us to manipulate the program to execute a function that wasn't
meant to be executed, or even execute code that we ourselves inject into the
program's memory.
