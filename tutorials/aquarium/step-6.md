# Combinatorial Search

Let's replace the mocked output with a real function computing the output.

Replace the program in the **Search Models** ingredient with the following content:
```asp
{water(X,Y)} :- group(X,Y,_).

:- row_clue(X,C), #count{Y : water(X,Y)} != C.
:- col_clue(Y,C), #count{X : water(X,Y)} != C.

:- water(X,Y), group(X,Y,G), group(X,Y',G), not water(X,Y').
:- water(X,Y), group(X,Y,G), group(X+1,Y,G), not water(X+1,Y).
```
