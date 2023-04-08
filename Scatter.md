---
date created: Thursday, January 19th 2023, 12:35:01 pm
date modified: Friday, March 24th 2023, 1:13:46 pm
---

# Scatter

The idea of the scatter is to send to each process data.

Now it's possible also to do it using `MPI`

## Laplace

P0 init the matrix by setting up the border to 1s and center to 0s.
- 1s => 1 on first line/column
- 0s => 0 on last line/column

```
recvbuf = zeros(10, 3)
tableau_global = ones(10, 12)

sendbuf = MPI.Ubuffer(tableau_global, 3*10)
MPI.scatter(sendbuf, recvbuf, MPI.comm_world)

recvbuf = zeros(10,3)
MPI.scatter(nothing, recvbuf, MPI.Comm_world)
```

### Communication

When the data is needed from other domain, then we need to communicate with other process or node.

## References
