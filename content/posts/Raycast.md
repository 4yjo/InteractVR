---
title: "Raycast"
date: 2023-02-14T16:49:35+01:00
draft: true
---

**Using Raycast to "blow wind" at objects**

*"Raycast in Unity is a Physics function that projects a Ray into the scene, returning a boolean value if a target was successfully hit. When this happens, information about the hit, such as the distance, position or a reference to the object’s Transform, can be stored in a Raycast Hit variable for further use."*
-- John French: Raycasts in Unity, made easy. Published on gamedevbeginner.com in June 2021. https://gamedevbeginner.com/raycasts-in-unity-made-easy/

The decision to use Raycasts allowed for a more controlled handling of events compared to using unity's rigid body - at least for me it soon became much easier to understand. 

*Visualize the Raycast with a Line-Renderer*
The raycast is implemented in the ```blowWind.cs``` script attached to the ventilator. I also attached a Line-Renderer-Component to the ventilator that visualises the ray for the players. 

<!-- TODO: Raycast1 img-->

The script differentiates between two kinds of "wind modes" that the players can change by tapping the touch button of the left controller. If the mode is changed successfully, the visualisation of the rendered line also changes in its thickness. The idea of the two wind modes is to metaphorically adjust the width of the wind-stream coming from the ventilator: With a broader wind-stream objects are moved. Objects that could be moved like that (some parts of the T-Objects as well as the kite) are placed on the layer "bigWind". The second wind mode, associated to the layer "smallWind" and used for all edges of the T-Object, can be thought of impulses that make obejcts rotate. 

*Using a Layer Mask to controll which objects can be hit*
The script checks the layer of the hit object using a Unity LayerMask. It is important that colliders are attached to the parts of the objects that should be hit. The video shows a test of my layer mask. If an object was placed on either the "bigWind" (left cube), "smallWind" (middle cube) or "objTask" (right cube) layer the color of the ray was changed from red to blue.


<!-- TODO: Insert Gif -->

 Using the layer mask also solved a problem, I had earlier: My Raycast did not cast all objects along its length, so when the kite was moved through the start banner in the beginning of the game, the raycast got "caught" in the collider of the start banner and the kite could not be moved any further. As the start banner is on the default layer, it is ignored by the raycast with the layer mask. 

*Using tags for game objects to define assigned interactions*
In the second step the objects I wanted to allow the player to interact with (including the kite) were assigned tags that helped to specify actions. For example, if the hit object had the Tag "impRight", the object should rotate as if it was hit by an wind impulse on the right. 

<!-- TODO: Raycast2 img-->



A special case was the player forward movement, that occured when the middle part was hit. Its collider is tagged "accKite" but instead of just giving one instruction the script uses a mapping (as described in the post on locomotion) to differentiate between four directions (forward, -forward, right, -right). This allowed to safely navigate through the parcour.

<!-- TODO: Raycast3 img && add code -->

