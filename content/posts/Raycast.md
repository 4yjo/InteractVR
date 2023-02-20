---
title: "Raycast"
date: 2023-02-14T16:49:35+01:00
draft: true
---

**Using Raycast to "blow" wind at objects**


The decision to use Raycasts allowed for a more controlled handling of events compared to the Unity Physics - at least for me it soon became much easier to understand. 

<!-- TODO: Introduction to Raycast -->


The raycast is implemented in the ```blowWind.cs``` script attached to the ventilator. I also attached a Line-Renderer-Component to the ventilator that visualises the ray for the players. 
The script differentiates between two kinds of "wind modes" that the players can change by tapping the touch button of the left controller. If the mode is changed successfully, the visualisation of the rendered line also changes its thickness. The idea of the two wind modes is to metaphorically adjust the width of the wind-stream coming from the ventilator: With a broader wind-stream objects are moved. Objects that could be moved like that (some parts of the T-Objects as well as the kite) are placed on the layer "bigWind". The second wind mode, associated to the layer "smallWind" and used for all edges of the T-Object, can be thought of impulses that make obejcts rotate. 
The script checks the layer of the hit object using a Unity LayerMask. It is important that colliders are attached to the parts of the objects that should be hit. Using the layer mask also solved a problem, I had earlier: My Raycast did not cast all objects along its length, so when the kite was moved through the start banner in the beginning of the game, the raycast got "caught" in the collider of the start banner and the kite could not be moved any further. As the start banner is on the default layer, it is ignored by the raycast with the layer mask. 

<!-- TODO: hier bilder aus final pres. einbinden-->

In the second step the objects I wanted to allow the player to interact with (including the kite) were assigned tags that helped to specify actions. For example, if the hit object had the Tag "impRight", the object should rotate as if it was hit by an wind impulse on the right. 

<!-- TODO: maybe add code example? -->

A special case was the player forward movement, that occured when the middle part was hit. Its collider is tagged "accKite" but instead of just giving one instruction the script uses a mapping (as described in the post on locomotion) to differentiate between four directions (forward, -forward, right, -right). This allowed to safely navigate through the parcour.
