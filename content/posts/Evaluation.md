---
title: "Evaluation"
date: 2023-02-14T17:52:29+01:00
draft: true
---

** Evaluation**

The game was tested by two people (excluding the developer). They were asked to play the game for one round of the parcours and afterwards filled in a short questionnaire. While playing, the following game logs were collected.

*Game Log - Design & Results*
Game logs of the two tests and the scores achieved by the (more practiced) developer as reference: 



"Time for Locomotion" describes the time needed to complete one round of the parcours excluding the time used for object interactions. 
"Total # coins" states the number of coins collected by the player. In total there were 69 coins in the scene but some at the end could not be collected because they were too high and the implemented player locomotion did not allow for jumping (this would be an interesting addition for future development).
"Time for Object Interaction" describes the total time used for all three object interaction tasks in one round of the parcours.
"Mean Error" states the mean offset of the opaque to the transparent object at the point the player hit the "done" button to submit their object interaction task results. As there were three tasks in total, the three offsets were summed up and then divided by three. 

<!-- TODO: insert game log table -->

*Game Log - Interpretation*
The results of the game log show that the locomotion was easy to understand and handle, even if you are play the game for the first time. The two tests had very similar times (one even slightly faster) compared to the reference. Also the coin count is well, considering the coins that could not be collected due to the lack of a jumping implementation. 
The object interaction on the other side differ a lot between the two testers. One was incredibly fast with a total of only 13.6 seconds for all three interaction tasks - but therefore highly unprecicse. The other player took some more time and had a better mean error. But the reference is even better, which suggests that some praciting is needed for the object interaction task. Further understanding on the implementation of this task can be gained from the answers of the questionnaire.

The testers were not told to prioritize speed or accuracy and set their own focus - one on collecting many coins, the other on precice fullfillment of coin-collection as well as the object tasks. 

*Questionnaire - Design & Results*
The questionnaire was designed to evaluate the subjective reception of the game. It asked if the players (on a scale from 1-5, 5 being total agreement) if the locomotion went smooth, the object interaction worked well and if they had overall fun playing the game. The questionnaire can be found [here:](
https://docs.google.com/forms/d/e/1FAIpQLSc8QGCH8cUqYHgZ8a7p9NkB4CPTzAOaaXaNBZEchupsYNxGxw/viewform?usp=sf_link)
There is no reference answer by the developer, as that would probably be highly biased ;)

<!-- TODO: insert questionnaire table -->
The perceived locomotion quality stated by the testers aligns with the results suggested by the game log: Both testers gave it 4/5 points and thus confirm that the implementation of the locomotion using the ventilator and the kite works well. 
The object interaction task got just 3/5 points. One tester stated in a commentary box, that they could not move the t-object up if it is located too close to the ground as they could not manage to position the ventilator accordingly. Here a modification of the implementation might help, e.g. in introducing a raycast bounce that allows the raycast to bounce from the ground and move the object upwards.
Another comment was that, it would be nice to receive the score for each object interaction task right after the task. 
The overall game experience was conceived as medium-fun (total of 3.5/5 points) but all testers stated that they would recommend the game to a friend. 

*Motion Sickness*
The questionnaire did not explicitly asked about motion sickness but the second tester stated that it could occur using the VR experience. They did not get a headache or other symptoms but felt a little swooshy after being in the VR. With that feedback I got back to the first tester to ask about motion sickness but they stated to not having had any problems at all. In introducing the exercise to the testers I told them to not go beyond any uncomfortable feelings and to just take off the headset if needed. Both testers successfully finished the parcours without interruptions. 
