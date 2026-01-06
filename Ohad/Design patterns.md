# Creational
## Factory
create objects from a superclass view.
e.g. create Shape but that shape will be internally routed to square, triangle etc. 

# Behavioral
## Observer
subscription model; an object (implements listener) can subscribe to the changes in a different object.

## Template
treat algorithm as steps, each step can be customized. 
so revealing a tile, since it is different per type of tile, will have its own custom behavior. but they all follow the same sequence of steps. 
implemented using abstract class.