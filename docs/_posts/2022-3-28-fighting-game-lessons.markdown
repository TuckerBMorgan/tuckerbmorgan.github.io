---
layout: post
title:  "Fighting game postmortum"
date:   2022-03-28 19:06:03 -0700

categories: Game thoughts
---

Over the past few months I built a [fighting game](https://github.com/TuckerBMorgan/StormFighting), and I wanted to talk about some of the lessons I picked up.

1. Rollback is the future.<br>
I got the chance to use a really good library [GGRS](github.com/gschup/ggrs) which is an all rust implementation of [GGPO](https://en.wikipedia.org/wiki/GGPO). Rollback, quickly, is a method of handling lag and input in
such a way that the game state will get rollback and forth as the game gets inputs it might have lost from the other player. Working with it has been a utter delight. Both the library and the just the concept of rollback. Allowing the developer to build the game without needing to think about the condition of the network, or how to handle dropped inputs is an amazing burden off of the mind, and I feel that more and more games will likely adopt this over time.
It has also been a hit with players, with modern fighting game(the community the techinque came out of) adaopting universily. Other types of games are taking this approch as well, shooters like Overwatch as an example, [source](https://www.youtube.com/watch?v=zrIY0eIyqmI).

2. Web might also be the future?<br>
The engine that I built the game in [Storm](github.com/mooman219/Storm) has a couple of opinions, one of which is is that it will work on Web. Rust already has a [WASM](https://en.wikipedia.org/wiki/WebAssembly) target, which is a sort of low level langugue for the web. After some careful choices, the engine is also able to run on the web. Most importanly, my code is generally not aware that it is running on the web(except one part where [Johan]https://github.com/johanhelsing/matchbox) helped me get websockets working). So, with the push of a button, an some wrangling of github my game was/is playable on the [web](https://tuckerbmorgan.github.io/StormFighting/). When I did a play test for my game, it was amazing to be a send my friends just a link and have them playing the full game, no downloading, if I need to update some part of the game, again, no patching, just refresh the page and the entire game is ready to play. 

3. Inspiration is a hell of a drug. <br>
From the start of the project I was lucky enough to be able to work with the wonderful author of my rollback libray. One night after pushing some work and testing it with them, they let me know that my project has given them energy to go and fix issues in the library after having become disinterested in the project. I was was ready to hear that my work had that effect on someone. It spured me to work more on it as well, and to keep making something that can keep them inspired. This alone made the project worth it, sure I have learned a whole bunch about how to lay out a fighting game, but discovering that my work can have such a positive effect on someone, that is the good [shit](https://c.tenor.com/65113pWCBGYAAAAd/snoop-dogg-smoke.gif). 
