# Aquarium

An optimization problem from the [LP/CP Programming Contest 2020](https://github.com/lpcp-contest/lpcp-contest-2020/).
It is described [here](https://github.com/lpcp-contest/lpcp-contest-2020/tree/main/problem-1).

Let's start by reading the description (reported below or clicking the above link).
After that, move to the next step.

## Description

> Your friend Neptune asks for your help to start a new business in the town.
> 
> You are given a square grid divided into blocks, and with numeric clues on each row and column.
> Water can be put into cells, obeying gravity low and a beauty criterion:
the water level in each block is one and the same across its full width.
> Clues are there to impose the number of filled cells in each row and column of the grid, as required by the customer who commissioned the work.
>
> Help Neptune to decide where the water should go.


## Input format

The first line contains one integer, `S`, the size of the grid.
The second line contains `S` integers, the column clues.
The third line contains `S` integers, the row clues.
The following `S` lines contain `S` integers each, denoting the block of each cell of the grid.


## Output format

`S` lines of `S` chars each, where `.` denotes a free cell, and `*` denotes a cell with water.


## Constraints

Instances are guaranteed to satisfy the following constraints:

* `S` between 6 and 30
* at most 100 blocks


## Example

Instance:

```
6
5 5 3 2 4 5
4 5 3 5 2 5
1 1 1 1 2 2
1 3 4 1 1 2
5 3 4 4 1 2
5 5 5 4 1 2
5 4 4 4 4 2
5 6 6 4 2 2
```

![instance](https://github.com/lpcp-contest/lpcp-contest-2020/raw/master/problem-1/example-in.png)

Expected output:

```
****..
**.***
.*..**
***.**
*....*
***.**
```

![output](https://github.com/lpcp-contest/lpcp-contest-2020/raw/master/problem-1/example-out.png)