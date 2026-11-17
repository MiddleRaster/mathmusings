---
layout: default
title: Wobbly Table Theorem
---

This is a fun little theorem and is useful if you find yourself in a restaurant trying to balance a cup of coffee on a wobbly table.  

More precisely, suppose you have a table with four legs such that the ends of the legs, the feet, form a square and the floor is continuous (no jumps) but not flat.  
In that case, the wobbly table theorem holds and says that you can stop the wobbling by turning the table less than 90 degrees.
Here's a simple sketch of a proof.

## Configuration 1

Without loss of generality, label the feet of the table A, B, C and D, clockwise, like this (viewed from above):  
A  **B**  
**C**  D  
Let's suppose B and C are firmly on the ground, while A and D are free to move up and down (hence the wobbling); in other words, the table is rotating/wobbling about a line through B and C.

Now one way to fix the problem is to place A on the ground, leaving D up in the air, and then by jamming on C, digging right into the floor (imagine it's made of dirt loose enough to be affected by the jamming), bring D down so that it just touches the floor.  

Problem solved, but it's not be ideal for the restauranteur who might object to a hole in his floor.


## Configuration 2

There's a better way.  
First, note that in configuration 1, we now have feet A, B and D just touching the surface of the floor, while C is dug in, below the level of the floor.  
Here's the better way:  rather than jamming on C, start rotating the table clockwise 90 degrees, but importantly, keep A, B and C precisely on the floor, while letting D do whatever (note it starts up in the air).
If we could complete that 90 degree rotation, D would end up where C was in configuration 1, dug into the floor.  
So D started up in the air and ended up under the level of the floor.
And that means (by the [intermediate value theorem](https://en.wikipedia.org/wiki/Intermediate_value_theorem)) that at some point during the rotation of the table, D just touched the floor.  

Voila. All four feet are on the floor, there's no wobbling and both the customer and the restauranteur are happy.  


### Limitations

For this sketch of a proof to work, the feet must form a square, so it doesn't work with rectangular tables, but fortunately, many (if not most) tables in restaurants are square.
For rectangular tables, see [Mathematical Table Turning Revisited](https://arxiv.org/pdf/math/0511490).  
Also, as mentioned before, the floor can't have discontinuities, which also is typical in restaurants (unless you're trying to balance a table on a staircase or something).  
Finally, the theorem guarantees that the table won't wobble, not that it's perfectly horizontal.
Still, if you were thinking of fixing the wobbling with a napkin, turning it a bit will work just fine.

### Final Thoughts

I have a chair in my kitchen that wobbles and by applying the theorem I now have a non-wobbling chair, though it's angled a bit oddly.  Similarly, a square-topped table might end up angled oddly too, but a round-topped table would work nicely.



[Math Musings](/mathmusings)  
[MiddleRaster's Pages](/)
