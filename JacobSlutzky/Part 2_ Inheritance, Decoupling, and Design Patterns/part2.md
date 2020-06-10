# Part 2: Inheritance, Decoupling, and Design Patterns

In Part 1, we saw how we can use a combination of simple **if-statements** and some **basic OO concepts** like *inheritance* to build out a variety of features in code. 

Today, we're going to continue down that same path, and throw in some new concepts as well. 

Specifically, we're going to work on *inheritance*, *decoupling*, and *design patterns*.

## New Weapons

### Double Barreled Shotgun

Max ammo: 50
Damage: 120
It should use 2 rounds of ammunition per shot.
 
### Knife
The Knife is a Weapon, but it isn't a gun, so you might say that it has infinite ammo.
Damage: 10
 
### Pulse Rifle
Max ammo: 50
Damage: 300

When you shoot it, it **should require 5 seconds** to "recharge" *before you can shoot it again*.

`PulseRifle.Shoot()` should be a non-blocking call. 

In other words, even though the weapon requires 5 seconds to recharge, the code shouldn't wait or sleep or anything.

For example, if we wrote a **for-loop** to call `Shoot()` back-to-back thousands of times in a row, the pulse rifle should only call `Enemy.TakeDamage()` every 5 seconds. 

If 5 seconds hasn't elapsed since the last shot was fired, then `PulseRifle.Shoot()` should just return immediately and not call `Enemy.TakeDamage()`.

Hint:  You can check the current time using System.Diagnostics.Stopwatch (https://msdn.microsoft.com/en-us/library/system.diagnostics.stopwatch%28v=vs.110%29.aspx).

Question: How can we test the Pulse Rifle "recharge" behavior in a unit test, without making our unit test wait for several seconds between calls to the `Shoot()` method?  

Given what we saw about **constructor arguments** and **interfaces**, what are some ways that we could let the PulseRifle class use the "real" DateTime.Now property in production, but use a "fake" version in a test?