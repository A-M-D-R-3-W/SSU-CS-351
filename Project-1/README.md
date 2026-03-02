# Project 1

### 1. Which program is fastest? Is it always the fastest?

- Small nodes + optimization: `alloca.out` is fastest (see `logs/5-trials-MINMAX10.txt`).
- Large nodes (512, 4096): `malloc.out` is slightly faster (see `logs/6...` and `logs/7...`).

Across all trials, `alloca.out` is often fastest but not always; it depends on node size and compiler flags.

### 2. Which program is slowest? Is it always the slowest?

- `list.out` is usually the slowest. `new.out` is often close.

Not always, but `list.out` is most often the slowest in these logs.

### 3. Was there a trend in program execution time based on the size of data in each Node? If so, what, and why?

- Small payloads: allocation overhead matters more, so `alloca` wins.
- Large payloads: hashing/processing the data dominates, so all programs run similarly.

### 4. Was there a trend in program execution time based on the length of the block chain?

{Still need to reference logs with different block sizes.}

### 5. Consider heap breaks, what's noticeable? Does increasing the stack size affect the heap? Speculate on any similarities and differences in programs?

- `alloca.out` shows very few heap breaks (~69).
- `malloc`, `new`, `list` show many more breaks and increase with payload size (see `breaks` logs).

Stack size does not increase the heap.

### 6. Considering either the malloc.cpp or alloca.cpp versions of the program, generate a diagram showing two Nodes. Include in the diagram
### the relationship of the head, tail, and Node next pointers.
### show the size (in bytes) and structure of a Node that allocated six bytes of data
### include the bytes pointer, and indicate using an arrow which byte in the allocated memory it points to.

{Still need to add the diagram.}

### 7. There's an overhead to allocating memory, initializing it, and eventually processing (in our case, hashing it). For each program, were any of these tasks the same? Which one(s) were different?

- Allocation: different (`alloca` cheap, `malloc`/`new` cost more).
- Initialization & hashing: same work for same payload size and dominate for large payloads.
- Heap growth behavior: different (see breaks).

### 8. As the size of data in a Node increases, does the significance of allocating the node increase or decrease?

- Allocation matters less as payload grows. For big payloads, processing dominates.

Individual logs used:
- `logs/1...`, `logs/2...`, `logs/3...`, `logs/4...`, `logs/5...`, `logs/6...`, `logs/7...`