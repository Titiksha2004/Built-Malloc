I implemented a custom dynamic memory allocator in C, focusing on efficient heap management and reduced memory fragmentation. The allocator uses an explicit free list along with automated block coalescing to improve memory utilization and performance.

Features
Explicit Free List Management
Maintains a linked list of free memory blocks for faster allocation and deallocation.
Block Coalescing
Automatically merges adjacent free blocks to minimize external fragmentation.
Heap Management using sbrk
Directly interacts with the system heap using sbrk for low-level memory control.
Optimized Memory Utilization
Reduces fragmentation and improves allocation efficiency.
Design Details
Each block contains metadata (size, allocation status, and pointers for free list navigation).
Free blocks are stored in a doubly linked list for efficient insertion and removal.
Coalescing is performed during free() to merge neighboring blocks.
Allocation strategy ensures minimal splitting overhead while maximizing usable memory.
Functions Implemented
mm_malloc(size_t size) — Allocates memory block
mm_free(void *ptr) — Frees allocated block and triggers coalescing
mm_realloc(void *ptr, size_t size) — Resizes allocated block
Internal helper functions for:
Free list insertion/removal
Block splitting
Coalescing adjacent blocks
Performance Goals
Minimize external fragmentation
Improve throughput of allocation/deallocation
Efficient use of memory hierarchy
