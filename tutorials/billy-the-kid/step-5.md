# Visualization

Let's draw the input graph, and highlight the selected towns.
It would be great to have the possibility to also highlight one path at time.
So, let's first add a **Slider** ingredient taking the minimum and maximum values from the `path` predicate, and producing the `highlight_path` predicate.
After that, let's add a **Search Models** ingredient with the following rules:
```asp
g(node(T), label(T)) :- town(T).
g(node(T), color(red)) :- select(T).

g(link(X,Y), undirected) :- connected(X,Y), X < Y.

highlight_path(X,Y) :- highlight_path(P), path(P,I,X), path(P,I+1,Y), X < Y.
highlight_path(X,Y) :- highlight_path(P), path(P,I,Y), path(P,I+1,X), X < Y.
g(link(X,Y), color(green)):- highlight_path(X,Y).
```
Now let's add a **Graph** ingredient using the `g` predicate to obtain an interactive visualization.

Finally, to conclude the exercise, let's add a **Show** ingredient with the following directive:
```asp
#show selected(N) : N = #count{T : select(T)}.
```
The output is now in the required format, that is,
```asp
selected(2).
```