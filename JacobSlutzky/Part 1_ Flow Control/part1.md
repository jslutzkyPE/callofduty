# Part 1: Flow Control

For Part 1, we're going to implement some basic logic that could form the foundations of the game Call of Duty.

The skeleton project has a few basic classes as well as a couple unit tests. As it sits, there's not a whole lot of functionality. But that's where you come in. ;-)

For Part 1, you'll need to implement the following changes to the code. As you work through it, look at each requirement, and try to think of how to write one or more unit tests that could verify that each requirement has been met.

## Weapon requirements:

1. Implement the `Weapon.AddAmmo()` method. 
   * When we call AddAmmo, we should increment some kind of public variable that serves as a counter to track how much ammunition the weapon has left.
2. Modify `Weapon.Shoot()` method to **decrease the remaining ammunition** *each time it is called*.
   * Don't call Enemy.ReceiveDamage if the weapon is out of ammo.
   * Don't allow the remaining ammunition to drop below 0!
3. Add a new variable to the Weapon class to store the maximum amount of ammunition.
4. Modify the `AddAmmo()` method so that we can only add up to the maximum ammo. 
   * For example, if a weapon currently has 25 rounds of ammo, and it can store up to 30, then if we add 10 rounds of ammo, the weapon's ammo should now be set to its maximum of 30.
5. Modify the existing **Shotgun class** to have a *maximum of 50 rounds of ammunition*.
6. Create a new weapon called Bazooka.
   * It should provide damage of 500 points
   * It should have a maximum ammunition of 2.

## Enemy requirements:

1. Add a new variable to the Enemy class to **track if the enemy** is *alive or not*.
   * This field should toggle from true to false when the enemy's energy drops to 0.
2. Create a new Enemy called Tank.
   * This class will have special behavior--its `ReceiveDamage()` method **should not decrease the remaining energy counter** unless the weapon does *at least 500 units of damage*. 
   * In other words, the Bazooka can damage it, but if you shoot it with a shotgun, it shouldn't even make a dent!

## Concepts

This project will help you build your skills in:
* [conditional logic](https://en.wikipedia.org/wiki/Conditional_(computer_programming))
* [unit testing](https://en.wikipedia.org/wiki/Unit_testing)
* [OO principles](https://en.wikipedia.org/wiki/Object-oriented_programming) like: 
   * [encapsulation](https://en.wikipedia.org/wiki/Encapsulation_(computer_programming))
   * [inheritance](https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming))
   * [polymorphism](https://en.wikipedia.org/wiki/Polymorphism_(computer_science))

This concludes Part 1.  Review your implementation with your mentor before proceeding to Part 2.