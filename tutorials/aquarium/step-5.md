# Mock

Let's have a visualization of the output before working on how to produce the output!

Add a **Search Models** operation after ingredient #18 (the relational mapping of the input) with
```asp
water(1,1). water(1,2). water(1,3). water(1,4). water(2,1). water(2,2). water(2,4). water(2,5). water(2,6). water(3,2). water(3,5). water(3,6). water(4,1). water(4,2). water(4,3). water(4,5). water(4,6). water(5,1). water(5,6). water(6,1). water(6,2). water(6,3). water(6,5). water(6,6).
```

Also add `water/2` to the **Select Predicate** ingredient.

The only missing thing is **how to compute the output?**
