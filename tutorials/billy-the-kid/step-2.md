# How to start

The problem can be decomposed in two parts.
First of all, we need to compute all paths of `N` towns.
After that, we can guess the towns where to place our guards and check that they hit all paths.

## Undirected graph in input

The first example input is the following:
```asp
town(1).         
town(2).         
town(3).         
town(4).         
town(5).         
town(6).         
                 
connected(1,4).  
connected(1,2).  
connected(2,3).  
connected(3,4).  
connected(3,5).  
connected(4,5).  
connected(5,6).  
                 
townsintravel(3).
```

Since the graph is undirected, it is common practice to close the `connected/2` relation symmetrically.
In ASP Chef such a closure can be imposed by the **Symmetric Closure** operation.
Let's add it to the recipe and set `connected` as the input and closure predicate.

The **Output panel** now shows the following content:
```asp
__base64__("Y29ubmVjdGVkKFgsWSkgOi0gY29ubmVjdGVkKFgsWSkuCmNvbm5lY3RlZChZLFgpIDotIGNvbm5lY3RlZChYLFkpLg==").
```
Use the **Decode** button in the **Output panel** to makes the following visible:
```asp
connected(X,Y) :- connected(X,Y).
connected(Y,X) :- connected(X,Y).
```
So, essentially, the **Symmetric Closure** operation instantiates a template with the predicate renaming specified in the ingredient.
The rules are Base64-encoded and can be processed by other operations such as **Search Models** and **Optimize**.

**Optional:** Use the **Set as input** button in the **Output panel** to copy the current output to the **Input panel**. You will see the `__base_64__/1` encoding once again. Remove the **Symmetric Closure** ingredient from the recipe. This should clarify that it is possible to _attach_ rules to programs using `__base_64__/1` encoding.

 Copy the first example instance (reported above) in the **Input** panel. Now, add a **Search Models** operation.
The symmetric closure of `connected/2` is now part of the output:
```asp
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
Note that `__base64__/1` is not in the output because _it was consumed_ by the **Search Models** ingredient.
You can click on the **ECHO** button if you want to echo the `__base64__/1` atoms in the output.