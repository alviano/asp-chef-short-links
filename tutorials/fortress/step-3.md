# Obtain a Good Relational Representation

OK! We have the input in predicate `__cell__/3`, but in ASP we usually have more descriptive predicates.
Let's have another look at the input format:

> The first line contains two integers, the number `R` of rows, and the number `C` of columns in the map.
> The following `R` lines contain `C` integers each, denoting ordinary cells (`0`) or point-of-interests (`D`, with `D > 0`).

## Mapping via ASP

Add a **Search Models** ingredient with the following content:
```asp
size(Rows, Columns) :-
  __cell__(1,1,Rows),
  __cell__(1,2,Columns).

poi(I-1,J,V) :- __cell__(I,J,V), I > 1, V > 0.
```

## Clean Up via Low Code

Add a **Select Predicates** and select `poi` and `size` to obtain a much more readable representation of the input:
```asp
size(23,23).
poi(9,9,3).
poi(9,11,2).
poi(9,13,3).
poi(9,15,3).
poi(10,10,1).
poi(10,14,2).
poi(12,9,6).
poi(12,14,3).
poi(14,10,1).
poi(14,15,2).
poi(15,9,3).
poi(15,14,1).
```