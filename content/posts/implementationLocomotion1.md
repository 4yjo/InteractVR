---
title: "ImplementationLocomotion1"
date: 2022-12-20T10:59:47+01:00
draft: true
---

**Implementation of Locomotion**


Initially, I decided for a 3rd person player to reduce motion sickness. But after discussing the idea in class, I decided for a 1st person view as that allows for smoother camera motion. Therefore a kite has been added that should enable the player to use the fan to blow wind into the kite. The player then is attached to the kite.

 <img title="Altering sketch from 1st to 3rd person perspective implementation" alt="two pictures: The firs is showing a white fan pointed towards a yellow sphere, the second shows a hand holding a fan pointing towards a kite." src="/_gen/images/player_mod.png">


The first idea was to make the kite follow the y-axis position from the Ventilator. Even though that approach was a bit slow, it allowed the kite to be moved from left to right. Then a force was applied to move the kite forward. The player was attached to the kite as a child and thus followed its movement. 


