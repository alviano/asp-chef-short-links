# Mock

Why not?
Let's have a visualization of the output before working on how to produce the output!

Add two **Search Models** operation with
```asp
wall(12,3). wall(11,4). wall(13,4). wall(10,5). wall(14,5). wall(9,6). wall(15,6). wall(8,7). wall(16,7). wall(7,8). wall(17,8). wall(6,9). wall(18,9). wall(7,10). wall(17,10). wall(7,11). wall(16,11). wall(7,12). wall(15,12). wall(6,13). wall(15,13). wall(7,14). wall(16,14). wall(6,15). wall(16,15). wall(7,16). wall(11,16). wall(13,16). wall(15,16). wall(8,17). wall(10,17). wall(12,17). wall(14,17). wall(9,18). attack(1,1). attack(1,2). attack(1,3). attack(1,4). attack(1,5). attack(1,6). attack(1,7). attack(1,8). attack(1,9). attack(1,10). attack(1,11). attack(1,12). attack(1,13). attack(1,14). attack(1,15). attack(1,16). attack(1,17). attack(1,18). attack(1,19). attack(1,20). attack(1,21). attack(1,22). attack(1,23). attack(23,1). attack(23,2). attack(23,3). attack(23,4). attack(23,5). attack(23,6). attack(23,7). attack(23,8). attack(23,9). attack(23,10). attack(23,11). attack(23,12). attack(23,13). attack(23,14). attack(23,15). attack(23,16). attack(23,17). attack(23,18). attack(23,19). attack(23,20). attack(23,21). attack(23,22). attack(23,23). attack(2,1). attack(3,1). attack(4,1). attack(5,1). attack(6,1). attack(7,1). attack(8,1). attack(9,1). attack(10,1). attack(11,1). attack(12,1). attack(13,1). attack(14,1). attack(15,1). attack(16,1). attack(17,1). attack(18,1). attack(19,1). attack(20,1). attack(21,1). attack(22,1). attack(2,23). attack(3,23). attack(4,23). attack(5,23). attack(6,23). attack(7,23). attack(8,23). attack(9,23). attack(10,23). attack(11,23). attack(12,23). attack(13,23). attack(14,23). attack(15,23). attack(16,23). attack(17,23). attack(18,23). attack(19,23). attack(20,23). attack(21,23). attack(22,23). attack(22,22). attack(21,22). attack(20,22). attack(19,22). attack(18,22). attack(17,22). attack(16,22). attack(15,22). attack(14,22). attack(13,22). attack(12,22). attack(11,22). attack(10,22). attack(9,22). attack(8,22). attack(7,22). attack(6,22). attack(5,22). attack(4,22). attack(3,22). attack(2,22). attack(22,2). attack(21,2). attack(20,2). attack(19,2). attack(18,2). attack(17,2). attack(16,2). attack(15,2). attack(14,2). attack(13,2). attack(12,2). attack(11,2). attack(10,2). attack(9,2). attack(8,2). attack(7,2). attack(6,2). attack(5,2). attack(4,2). attack(3,2). attack(2,2). attack(22,21). attack(22,20). attack(22,19). attack(22,18). attack(22,17). attack(22,16). attack(22,15). attack(22,14). attack(22,13). attack(22,12). attack(22,11). attack(22,10). attack(22,9). attack(22,8). attack(22,7). attack(22,6). attack(22,5). attack(22,4). attack(22,3). attack(2,21). attack(2,20). attack(2,19). attack(2,18). attack(2,17). attack(2,16). attack(2,15). attack(2,14). attack(2,13). attack(2,12). attack(2,11). attack(2,10). attack(2,9). attack(2,8). attack(2,7). attack(2,6). attack(2,5). attack(2,4). attack(2,3). attack(3,3). attack(3,4). attack(3,5). attack(3,6). attack(3,7). attack(3,8). attack(3,9). attack(3,10). attack(3,11). attack(3,12). attack(3,13). attack(3,14). attack(3,15). attack(3,16). attack(3,17). attack(3,18). attack(3,19). attack(3,20). attack(3,21). attack(21,3). attack(21,4). attack(21,5). attack(21,6). attack(21,7). attack(21,8). attack(21,9). attack(21,10). attack(21,11). attack(21,12). attack(21,13). attack(21,14). attack(21,15). attack(21,16). attack(21,17). attack(21,18). attack(21,19). attack(21,20). attack(21,21). attack(4,3). attack(5,3). attack(6,3). attack(7,3). attack(8,3). attack(9,3). attack(10,3). attack(11,3). attack(13,3). attack(14,3). attack(15,3). attack(16,3). attack(17,3). attack(18,3). attack(19,3). attack(20,3). attack(4,21). attack(5,21). attack(6,21). attack(7,21). attack(8,21). attack(9,21). attack(10,21). attack(11,21). attack(12,21). attack(13,21). attack(14,21). attack(15,21). attack(16,21). attack(17,21). attack(18,21). attack(19,21). attack(20,21). attack(20,20). attack(19,20). attack(18,20). attack(17,20). attack(16,20). attack(15,20). attack(14,20). attack(13,20). attack(12,20). attack(11,20). attack(10,20). attack(9,20). attack(8,20). attack(7,20). attack(6,20). attack(5,20). attack(4,20). attack(20,4). attack(19,4). attack(18,4). attack(17,4). attack(16,4). attack(15,4). attack(14,4). attack(10,4). attack(9,4). attack(8,4). attack(7,4). attack(6,4). attack(5,4). attack(4,4). attack(20,19). attack(20,18). attack(20,17). attack(20,16). attack(20,15). attack(20,14). attack(20,13). attack(20,12). attack(20,11). attack(20,10). attack(20,9). attack(20,8). attack(20,7). attack(20,6). attack(20,5). attack(4,19). attack(4,18). attack(4,17). attack(4,16). attack(4,15). attack(4,14). attack(4,13). attack(4,12). attack(4,11). attack(4,10). attack(4,9). attack(4,8). attack(4,7). attack(4,6). attack(4,5). attack(5,5). attack(5,6). attack(5,7). attack(5,8). attack(5,9). attack(5,10). attack(5,11). attack(5,12). attack(5,13). attack(5,14). attack(5,15). attack(5,16). attack(5,17). attack(5,18). attack(5,19). attack(19,5). attack(19,6). attack(19,7). attack(19,8). attack(19,9). attack(19,10). attack(19,11). attack(19,12). attack(19,13). attack(19,14). attack(19,15). attack(19,16). attack(19,17). attack(19,18). attack(19,19). attack(6,5). attack(7,5). attack(8,5). attack(9,5). attack(15,5). attack(16,5). attack(17,5). attack(18,5). attack(6,19). attack(7,19). attack(8,19). attack(9,19). attack(10,19). attack(11,19). attack(12,19). attack(13,19). attack(14,19). attack(15,19). attack(16,19). attack(17,19). attack(18,19). attack(18,18). attack(17,18). attack(16,18). attack(15,18). attack(14,18). attack(13,18). attack(12,18). attack(11,18). attack(10,18). attack(8,18). attack(7,18). attack(6,18). attack(18,6). attack(17,6). attack(16,6). attack(8,6). attack(7,6). attack(6,6). attack(18,17). attack(18,16). attack(18,15). attack(18,14). attack(18,13). attack(18,12). attack(18,11). attack(18,10). attack(18,8). attack(18,7). attack(6,17). attack(6,16). attack(6,14). attack(6,12). attack(6,11). attack(6,10). attack(6,8). attack(6,7). attack(7,7). attack(7,17). attack(17,7). attack(17,11). attack(17,12). attack(17,13). attack(17,14). attack(17,15). attack(17,16). attack(17,17). attack(11,17). attack(13,17). attack(15,17). attack(16,17). attack(16,16). attack(16,13). attack(16,12).
```
and
```asp
__graph__(node(cell(I,J)),
  fx(J * 10), fy(I * 10)
) :- size(R,C), I = 1..R, J = 1..C.

__graph__(node(poi(I,J)),
  fx(J * 10), fy(I * 10),
  label(V),
  color(white),
  shape(circle)
) :- poi(I,J,V).

__graph__(node(cell(I,J)),
  fx(J * 10), fy(I * 10),
  color(transparent),
  label("⚔️")
) :- attack(I,J).

__graph__(node(cell(I,J)),
  fx(J * 10), fy(I * 10),
  color(brown)
) :- wall(I,J).

__graph__(defaults,
  node_shape(square),
  node_radius(5)
).
```
followed by a **Graph** operation.

Note that the first snippet of ASP code encodes a solution for the example input.
It is not important how you obtain it.
You may compute it by hand.
What is important is that we now have a nice visualization also for the output.

The only missing thing is **how to compute the output?**
