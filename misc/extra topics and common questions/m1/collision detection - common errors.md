
# Collision detection - Common errors



## 1. Mixing units

![mixing-units-diagram](./collision%20detection%20-%20mixing%20units%20-%20diagram.png)
![mixing-units-example](./collision%20detection%20-%20mixing%20units%20-%20example.png)


Best option: don't mix different types of units.
- If you use vw/vh like we do in class, use vw/vh for all units (vw for all horizontal units like the width and positionX & vh for all vertical ones).
- If you prefer to use pixels (for example, it can make easier to add images), then use px for all


Alternative:
- another solution is to convert all to the same units when you do collision detection (ie. if you have the width in px, calculate how much is that in vw, which you can do in js).



## 2. Images with transparent background

![transparent-bg](./collision%20detection%20-%20transparent%20bg.png)
