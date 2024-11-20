# Compute all paths

One way to compute one path is to guess a starting town, and then expand the path with further guesses on not-already-visited towns.
And once we know how to compute one path, we can simply enumerate all of them.

Before we produce all paths in different models, let us add a **Store** ingredient to save the expanded input we have at the moment.

After that, add a **Search Models** ingredient with the following rules:
```asp
{path(1,T) : town(T)} = 1.
{path(I+1,T') : connected(T,T')} = 1 :- path(I,T), townsintravel(TOT), I < TOT.
:- path(I,T), path(J,T), I < J.

in_path(T) :- path(_,T).
```
Enumerate all models by asking for 0 models and disabling the **RAISE ERROR** option.
Note that there are 22 models or paths, but some of them comprise the same set of towns.
Verify it by adding a **Select Predicates** ingredient learving only `in_path` and `path` in the output.

ASP Chef provides a **Unique** operation to remove **duplicate** models, where two models are considered equals if they have the same elements in the same order.
So, let's add a **Sort Canonically** ingredient followed by a **Unique** operation, and exclude `path` from the uniqueness check (if you want, exclude it also from the sorting criteria).
Only 9 models are now produced in output.

We can now add a **Merge** ingredient to pack all models in a single model.
The new model carries sufficient information to index the original models.
And we can use a **Search Models** operation to reshape the facts in a more understandable format:
```asp
in_path(M,T) :- __model__(M, in_path(T)).
path(M,I,T) :- __model__(M, path(I,T)).  % for the graph
```

Let's add a **Select Predicates** ingredient to discard the `__model__` predicate.

Finally, let's add a **Restore** ingredient for the key of the **Store** ingredient we added previously.
Let's also click on the **ECHO** button to forward the facts representing the paths we just computed.

The output should now be the following:
```asp
in_path(1,1).
in_path(1,2).
in_path(1,3).
in_path(2,1).
in_path(2,2).
in_path(2,4).
in_path(3,1).
in_path(3,3).
in_path(3,4).
in_path(4,1).
in_path(4,4).
in_path(4,5).
in_path(5,2).
in_path(5,3).
in_path(5,4).
in_path(6,2).
in_path(6,3).
in_path(6,5).
in_path(7,3).
in_path(7,4).
in_path(7,5).
in_path(8,3).
in_path(8,5).
in_path(8,6).
in_path(9,4).
in_path(9,5).
in_path(9,6).
path(1,1,3).
path(1,2,2).
path(1,3,1).
path(2,1,4).
path(2,2,1).
path(2,3,2).
path(3,1,3).
path(3,2,4).
path(3,3,1).
path(4,1,5).
path(4,2,4).
path(4,3,1).
path(5,1,2).
path(5,2,3).
path(5,3,4).
path(6,1,5).
path(6,2,3).
path(6,3,2).
path(7,1,5).
path(7,2,3).
path(7,3,4).
path(8,1,3).
path(8,2,5).
path(8,3,6).
path(9,1,4).
path(9,2,5).
path(9,3,6).
connected(1,4).
connected(1,2).
connected(2,3).
connected(3,4).
connected(3,5).
connected(4,5).
connected(5,6).
connected(6,5).
connected(5,4).
connected(5,3).
connected(4,3).
connected(3,2).
connected(2,1).
connected(4,1).
town(1).
town(2).
town(3).
town(4).
town(5).
town(6).
townsintravel(3).
```