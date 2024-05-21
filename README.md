# C-allocation

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

The code above allocates contiguous memory to 25 elements the size of the float. If space is insufficient, it again returns a NULL pointer.
