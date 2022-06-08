# Classical Mechanics Simulations

Below, I document some astronomical simulations. This was done using Newtonian, Lagrangian, and/or Hamiltonian mechanics. 

## 1) 2D *N*-Body Simulation (WITH Collisions)

![](https://media.giphy.com/media/vIvLXYWTT9ZxPYuDuS/giphy.gif).

NOTE: this simulation does not take relativity into account
 
In this simulation, I let 10 objects with the same mass interact via gravity and observe their interaction. This code works with any number of particles (hence the title of *N*-body simulation). As mentioned in the title, this program takes collisions into account. Below, I list some of my thoughts about this project and some specifics.

- Each collision is considered a perfectly elastic one. In my initial draft of the code, the collisions were not elastic (and of course not perfectly inelastic either). What I did was multiply the original kinetic energy *T* with a constant *C*, which was a value between 0 and 1, to portray how much energy I had left after a collision. However, after taking the conservation of momentum and energy equations and solving for one of the final velocities (which resulted in a quadratic equation), I realized that the discriminant of that equation is not always positive or 0. I do not understand the physical interpretation of such a collision so I decided to find ways to make sure that disciminant was always >= 0. After trying a bunch of different equations, I landed on two conditions: all the masses have to be the same and the constant *C* has to be equal to 1. These rules are limitations of this code but I would like to change these in the future after understanding where the negative disciminant comes from. 

- Another limitation of this code is *n*-way collisions, where *n* >= 3 (Note that this *n* != *N*). This is because I have *n* unknowns (the final velocities of the particles involved in the collision) and 2 equations (conservation of momentum and energy). I tried looking for some equations online but did not come across any. If I figure out this problem, I will fix it.

- The mass of each particle was 10^(5) kg.

- The softening parameter was 10 m.

- The initial positions and velocities were randomized, with each following a bell curve with mean 0 and variance of 1.
 
