---
title: "Implementation of Locomotion"
date: 2022-12-20T10:59:47+01:00
draft: false
---

**Implementation of Locomotion**


Initially, I decided for a 3rd person player to reduce motion sickness. But after discussing the idea in class, I decided for a 1st person view as that allows for smoother camera motion. Therefore a kite has been added that should enable the player to use the fan to blow wind into the kite. The player then is attached to the kite.

 <img title="Altering sketch from 1st to 3rd person perspective implementation" alt="two pictures: The firs is showing a white fan pointed towards a yellow sphere, the second shows a hand holding a fan pointing towards a kite." src="./_gen/images/player_mod.png"/>

![From 1st to 3rd person player implementation](/sketch_locomotion.png)
<img src = "/sketch_locomotion.png">

The first idea was to make the kite follow the y-axis position from the Ventilator. Even though that approach was a bit slow, it allowed the kite to be moved from left to right. Then a force was applied to move the kite forward. The player was attached to the kite as a child and thus followed its movement. 


<!-- TODO: hier Gif einfügen -->

This did not work well, as it did not allow the kite to rotate. The player could only move in forward direction and do zig-zag movements to the left and right but it was impossible to turn around a corner. 

In the next iteration I managed to rotate the kite in a smooth circle according to the angle of rotation of the left controller. Therefore I attached the kite as child to an invisible cylinder that is used to recenter the rotation. Now, people can move the controller and the kite follows its orientation as if it is blown by wind. This worked well and very smooth as long as I used it. But as the values for mapping the controller rotation to the kite rotation were just retrieved by trial-and-error they were highly customed to my physiology and how I hold the controller. I was thinking about introducing a pre-task that would ask the make certain movements in with the controller to learn user specific values. 
But another problem occured with this way of implementation: The player rotation did not allign with the rotation of the field of view that was constantly changed by the users head movement. This lead to the problem that when turning around the second corner of the parcour there was a mismatched positioning of the player and the kite: The kite now needed to be positioned behind the players back to generate forward movement, which made it nearly impossible to controll the direction the player was moving to. 
To fix those problems I re-implemented the rotation of the kite using Raycast and Colliders. (Refer to the blog post about Raycast for more information). 
In the final implementation I am mapping the controllers y-rotation (in euler angles) to one of four areas as follows:

Then, in the script the players forward direction is specified. 

<!-- TODO: hier Bild aus Präsi (-45/90) einfügen -->

To add movement I used the index trigger from the controller. It felt natural to use that, as it would be a similar hand movement if the user was holding a ventilator or hairdryer instead of the controller. 

The final implementation allows for precice navigation and testers had a good understanding of how to use the ventilator and the kite togehter for locomotion. 





```
if((OVRInput.Get(OVRInput.Axis1D.PrimaryIndexTrigger))> 0f) 
        {
            this.transform.Translate(transform.forward*0.1f);
        }
```
