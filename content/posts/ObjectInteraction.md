---
title: "ObjectInteraction"
date: 2023-02-14T16:49:46+01:00
draft: true
---

** Implementation of Object Interaction**

There are three object interaction tasks within the parcours. Each spawns two t-shaped objects in random position and rotatin. One is slightly transparent, the other is opaque. The users have to rotate and translate the position of the opaque object to make it fit the transparent ones. In the end the accuracy is measured by calculating the offset of the different parts of the transparent object from the opaque one. This task was already implemented as part of the parcours. It is started when a start button is hit, then a timer measures the time of the task. If the player is content with the movement and rotation, they hit the done button to submit the task results and continue in the parcours. 

In my implementation the player can rotate the objects using the "small Wind" mode to send wind impulses to different edges of the shape. As the order of rotation for each axis is decided by the players, all rotations can be achieved and gimbal lock is omitted. 

To make the objects' position fit, the player can use the "big Wind" mode to move the object in the direction of the ray. It might be necessary to first use the kite to position oneself in the right angle in front of the object. 

<!-- TODO: Insert video or gif that shows object rotation and movment -->

The implementation strongly relays on the mechanics of the blowWind script. Those are described in detail in the blog post about raycasts.
