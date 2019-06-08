Add your answers to the Algorithms exercises here.

## Exercise 1:

a) O(n).  At first glance, it seems like O(n^3) but the loop stops at n^3 and steps by n^2 so it seems like it will
always run n times no matter the value of n.

b) O(n^3).  The last nested loop at first glance seems like another O(n), making this O(n^4), but we can see the range
starts at k and goes to 10 + k.  That's actually an O(c), so the entire thing ends up being O(n^3).

c) O(n).  This function calls itself n times unless you give it a value less than 0, at which point it might call itself infinity times.


## Exercise 2:

- n = height of building
- f = minimum egg-breaking height

Initial thoughts: Building floors is an ordered list: [0,1,2,3...n] and this exercise seems like an O(log(n)) problem
where we're going to be cutting the set of floors in half on each iteration.

Pseudocode / Plain English Solution:

1) Given a list of floors from 0 to n, go to the middle floor and drop an egg.
2) if the egg breaks, do it again but with floors 0 to the current floor. (set n to the previous middle floor)
3) if the egg doesn't break, do it again but with the current floor as the minimum floor and n as the highest floor.
4) the 'middle floor' is the result of: `(number of remaining floors) // 2`, so for any results with decimals, drop the
numbers after the decimal.
5) repeat this process until you run out of floors to test.
6) if the final floor breaks the egg, then that's the minimum break height.
7) if the final floor doesn't break the egg, then the minimum break height is a floor higher (if that floor exists)
otherwise we don't know what the minimum break height is.

