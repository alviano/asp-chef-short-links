# Obtain a Good Relational Representation

OK! We have the input in predicate `__cell__/3`, but in ASP we usually have more descriptive predicates.
Let's have another look at the input format:

> The first line contains one integer, `S`, the size of the grid.
> The second line contains `S` integers, the column clues.
> The third line contains `S` integers, the row clues.
> The following `S` lines contain `S` integers each, denoting the block of each cell of the grid.


## Mapping via ASP

Add a **Search Models** ingredient with the following content:
```asp
size(Size) :- __cell__(1, 1, Size).
col_clue(J, Clue) :- __cell__(2, J, Clue).
row_clue(J, Clue) :- __cell__(3, J, Clue).
group(I-3,J,G) :- __cell__(I,J,G), I > 3.
```

## Clean Up via Low Code

Add a **Select Predicates** and select all predicates but `__cell__` to obtain a much more readable representation of the input:
```asp
size(6).
col_clue(1,5).
col_clue(2,5).
col_clue(3,3).
col_clue(4,2).
col_clue(5,4).
col_clue(6,5).
row_clue(1,4).
row_clue(2,5).
row_clue(3,3).
row_clue(4,5).
row_clue(5,2).
row_clue(6,5).
group(1,1,1).
group(1,2,1).
group(1,3,1).
...
```