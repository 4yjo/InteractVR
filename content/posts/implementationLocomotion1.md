---
title: "ImplementationLocomotion"
date: 2022-12-20T10:59:47+01:00
draft: false
---

**Implementation of Locomotion**


Initially, I decided for a 3rd person player to reduce motion sickness. But after discussing the idea in class, I decided for a 1st person view as that allows for smoother camera motion. Therefore a kite has been added that should enable the player to use the fan to blow wind into the kite. The player then is attached to the kite.

 <img title="Altering sketch from 1st to 3rd person perspective implementation" alt="two pictures: The firs is showing a white fan pointed towards a yellow sphere, the second shows a hand holding a fan pointing towards a kite." src="./_gen/images/player_mod.png"/>

![From 1st to 3rd person player implementation](./_gen/images/player_mod.png)
![From 1st to 3rd person player implementation](/posts/player_mod1.jpg)
The first idea was to make the kite follow the y-axis position from the Ventilator. Even though that approach was a bit slow, it allowed the kite to be moved from left to right. Then a force was applied to move the kite forward. The player was attached to the kite as a child and thus followed its movement. 


<!-- TODO: hier Gif einfügen -->

This did not work well, as it did not allow the kite to rotate. The player could only move in forward direction and do zig-zag movements to the left and right but it was impossible to turn around a corner. Thus I took a deeper look in implementing rotations in Unity. For more information see the post to this topic.

In the end I managed to rotate the kite in a smooth circle according to the angle of rotation of the left controller. So people can move the Controller as the fan and the kite follows its orientation as if it is blown by wind. 

To add movement I used the index trigger from the controller. It felt natural to use that, as it would be a similar hand movement if the user was holding a ventilator or hairdryer instead of the controller. If there is time left in the end, I would like to adjust the speed in relation to how much the trigger is pressed. This should be possible, as the oculus controller returns a float for the trigger. 
But for now, it is just moving the player if the trigger is pressed: 

```
if((OVRInput.Get(OVRInput.Axis1D.PrimaryIndexTrigger))> 0f) 
        {
            this.transform.Translate(transform.forward*0.1f);
        }
```
