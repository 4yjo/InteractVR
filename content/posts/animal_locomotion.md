---
title: "First ideas: Locomotion in nature and science-fiction"
date: 2022-11-16T13:03:25+01:00
draft: false
---

**Nature's source of inspiration: Researching Locomotion in animals** 
First I brainstormed and researched different types of locomotion in anmimals to find inspiration for the locomotion implementation in VR:
- swimming: either by pushing away water with arms/legs or by body movement 
- crawling: similar movements as in swimming, but on land
- flying: up & downward movement to keep up in the air
- walking/running: forward movement with legs/feet 
- jumping

And I read more about how four-legged animals walk:

 *"It turns out that all four-legged animals step with their left hind leg followed by their left foreleg. Then they step with their right hind leg followed by the right foreleg, and so on. Animals differ from one another only in the timing of that stepping."* 
    -- Cell Press. "How Does A Dog Walk? Surprisingly, Many Of Us Don't Know." ScienceDaily. ScienceDaily, 29 January 2009.  https://www.sciencedaily.com/releases/2009/01/090126121348.htm 

But the adaption of four-legged locomotion seemed hard to translate to the state-of-the-art VR Tracking systems where only the two controller or hands are detected. Furthermore one important aim for my locomotion was, that the players easily understand it and four inputs would lead to high complexity.

**Contained Movement Mapping: Inspiration from the Movie "HER"**
Then I looked into the 2013 movie "Her" by Spike Jonze from 2013. The story is situated in a science-fiction world not too far away in the future. We accompany the main character in his life that gets more and more intertwined with technology as he starts using an AI-based operating system that assists him with his daily tasks but also gets very connected on a personal level. In the beginning of the movie there is one scene where the main character plays a computer game, which has very interesting game mechanics: It is an AR Game, where an overlay screen is present in the characters living room. He is watching the 3rd person player from behind and can steer his movement with small hand-gestures. The faster he moves his fingers, the faster the game-character is running through the scene. The orientation is mapped from the hand-angle, which allows precice and natural translation. Another advantage seems to be the limited space needed for the hand-guestures that prevents fatigue due to the so called gorilla-arms.
    In the movie all further interactions like object interactions are implemented with speech recognition that allows the player to talk to the game-charakter. 
