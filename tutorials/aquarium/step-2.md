# How to start

Let's start by understanding the input format.

## Input format

The first line contains one integer, `S`, the size of the grid.
The second line contains `S` integers, the column clues.
The third line contains `S` integers, the row clues.
The following `S` lines contain `S` integers each, denoting the block of each cell of the grid.


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

## Parsing

Copy the CSV content in the **Input panel**, and click the **ENCODE** button.
You should see a Base64-encoded content in the **Output panel**.

Now add a **Parse CSV** ingredient and specify **SPACE** as the separator.
The output is now in a format we can easily process with ASP rules:
```asp
__cell__(1,1,6).
__cell__(2,1,5).
__cell__(2,2,5).
__cell__(2,3,3).
...
```