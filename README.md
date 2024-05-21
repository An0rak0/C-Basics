# C-allocation
In C, we can allocate memory dynamically. We do this by creating pointers that hold the address of a block of memory. These pointers don't do anything else, they just point.

## Memory allocation/recalling
Methods of allocation/reallocation and memory recalling are: malloc, calloc, free and realloc.

### Malloc
The syntax for malloc (memory allocation) is:

```
ptr = (cast-type*) malloc(byte-size) 
```

Example:

```
ptr = (int*) malloc(100 * sizeof(int)) 
```

This code is saying that it will allocate 100 x the size int, which is 4 bytes. This means it allocates 400 bytes. If size is insufficient, it returns a NULL pointer. Malloc is useful when a user is inputing information that isn't of a specified value, and therefore always needs different amounts of memory.

### Calloc
The syntax for calloc (contiguous allocation) is:

```
ptr = (cast-type*)calloc(n, element-size)
```

Here, n is the number of elements and element size is the size of each element.

Example:

```
ptr = (float*) calloc(25, sizeof(float))
```

The code above allocates contiguous memory to 25 elements the size of the float. If space is insufficient, it again returns a NULL pointer. Calloc is slower, but does initialize the memory to 0.

### Realloc
The syntax for realloc (re-allocation) is:

```
ptr = realloc(ptr, newSize)
```

Above, ptr is reallocated with a new amount of memory, newSize. Realloc must be used in conjuction with, or after, malloc/calloc.

Example:

```
int* ptr = (int*)malloc(5* sizeof(int))

ptr = realloc(ptr, 10* sizeof(int))
```

The code snippet above performs 2 actions: it dynamically allocates a chunk of memory worth 5 times the size of int (4 bytes). It then re-allocates this memory (worth 20 bytes) to 10 times the size of int. The re-allocated size is 40 bytes.

### Free
The syntax for free is:

```
free(ptr)
```

Like realloc, this must be used in conjuction with, or after, malloc/calloc.

Example:

```
int* ptr = (int*)malloc(5* sizeof(int))

free(ptr)
```

The code example for free, is similar to realloc, where it first allocates the memory, but instead of changing the size of ptr, it removes the memory entirely, 'freeing it'.
