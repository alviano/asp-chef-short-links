# Combinatorial search and optimization

We can now guess the towns to monitor, check that they hit all paths, and minimize their number.
Let's add an **Optimize** ingredient with the following rules:
```asp
{select(T)} :- town(T).
ok(P) :- select(T), in_path(P,T).
:- in_path(P,_), not ok(P).

:~ select(T). [1@1, T]
```

The output is expanded with 
```asp
select(3).
select(4).
ok(1).
ok(2).
ok(3).
ok(4).
ok(5).
ok(6).
ok(7).
ok(8).
ok(9).
__costs__((2,)).
```
So, in this case we selected two towns.