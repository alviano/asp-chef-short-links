# Combinatorial Optimization

Let's replace the mocked output with a real function computing the output.

Remove the **Search Models** ingredient with the hard-coded output and add an **Optimize** operation with the following content:
```asp
grid(X,Y) :- size(R,C), X = 1..R, Y = 1..C.

{wall(X,Y)} :- grid(X,Y).
:- poi(X,Y,D), wall(X',Y'), |X-X'| + |Y-Y'| < D.

delta(X,Y) :- X = -1..1, Y = -1..1, |X|+|Y| = 1.

attack(X,Y) :- size(R,C), X = 1, Y = 1..C, not wall(X,Y).
attack(X,Y) :- size(R,C), X = R, Y = 1..C, not wall(X,Y).
attack(X,Y) :- size(R,C), Y = 1, X = 1..R, not wall(X,Y).
attack(X,Y) :- size(R,C), Y = C, X = 1..R, not wall(X,Y).
attack(X+DX,Y+DY) :- attack(X,Y), delta(DX,DY), grid(X+DX,Y+DY), not wall(X+DX,Y+DY).
:- poi(X,Y,_), attack(X,Y).

:~ wall(X,Y). [1@2, X,Y]
:~ attack(X,Y). [-1@1, X,Y]
```
Note that you can add an **Operations panel** before an ingredient by clicking the button with the square and the up arrow.
This way, you can add an operation in the middle of the recipe.

Also note that the default algorithm for combinatorial optimization is _linear search sat-unsat_, and it takes really a lot of time for this encoding.
Before the **Optimize** ingredient, add a **Set Optimization Strategy** operation.
I already set my favorite strategy, but feel free to experiment with something else.