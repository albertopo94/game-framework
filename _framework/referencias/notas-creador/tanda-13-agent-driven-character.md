Capítulo 1: Making art for a game, beyond the first prompt
0:000 segundosI'm working on a game project right now to see what it's like when you build a game with AI and keep going way beyond that initial prompt and put actually a decent amount of effort into it.
0:1010 segundosAnd there are a lot of lessons that I've learned along the way.
0:1212 segundosAnd one of them I wanna share with you today is how to create art that really works easily in just about any game and how cheap and easily you can do it.
0:2121 segundosThis character right here was just a concept.
0:2323 segundosIn fact, it started as me just asking AI for a couple of concepts so that I could put this video together, ask for 10 concepts.
0:3232 segundosSo I could pick the one that I thought would be maybe the most interesting and also fit into what I was building. There are a lot of different choices here.
Capítulo 2: Choosing an initial direction
0:4040 segundosI kind of liked the bee one, but I honestly just thought it looked a little bit strange for my game.
0:4646 segundosI still might put it in because the tech stuff on it looked really cool.
0:4848 segundosI was thinking maybe I'll just steal the tech items and move them over to something else.
0:5353 segundosBut the Tidal Anchor guy, the number 10, seemed to be coolest. It seemed like the thing kind of fit in there.
0:5858 segundosIt'd be a fun enemy to fight against, has a big shield and a kind of a lance like a Stargate weapon and really do some fun stuff with it.
1:061 minuto y 6 segundosAnd it seemed kind of big and beefy and didn't match a lot of the other characters that I already had.
Capítulo 3: Prompt 1 — document the process
1:111 minuto y 11 segundosAnd you can see the actual prompt here was just, I'd like to do a video about your process. Can you help me with that? I'd like a list of the skills you use to do art and some info about them.
1:201 minuto y 20 segundosAnd then a new concept of a unique warrior sci-fi character that's somewhat cybernetic. Do 10 of them and record the sheets along with my pick.
1:291 minuto y 29 segundosDo screenshots for the video is just fine.
1:321 minuto y 32 segundosAnd then use the generation process, but record it locally So there's a video of the entire thing going on. You can use it, OBS or whatever. I didn't really care.
1:401 minuto y 40 segundosSo don't do whatever it wants. Record the Tripo process where we do the character creation and generation. Talk about that in a minute.
1:471 minuto y 47 segundosAnd then the output, the iteration, and all of the clips together so that we can put it together and show it off. And you can see here the concepts again.
1:551 minuto y 55 segundosYou can see it just replied that it's going to make a documented character build with a short guide of the skills, some distinct warrior concepts, and so on.
2:032 minutos y 3 segundosAnd then it's created them and put them into the view.
2:062 minutos y 6 segundosLet me pick the one that I wanted and like I said, I picked number 10. And here are the skills that it's using. It's a no-route right away.
Capítulo 4: Skills and setup
2:132 minutos y 13 segundosImageGen. It's using computer use so that it can take over and run my browser and a couple other things and run some stuff in Blender.
2:212 minutos y 21 segundosUnity CLI and the diagnosing-bugs one, which is from Matt Pocock.
2:262 minutos y 26 segundosAgain if you want to get that full list and just the entire setup for it, you can just download it. I'll have the AI editor put that down there for you.
2:342 minutos y 34 segundosOnce I did that, I got that first character back and you can see it looks really cool, matched with what I wanted but then I realized that I had forgotten to tell it one of the most
Capítulo 5: Prompt 2 — separate the equipment
2:432 minutos y 43 segundosimportant parts which is to separate out the character from the actual equipment so that way we can swap out equipment.
2:502 minutos y 50 segundosSo I told him for this process, make the equipment toggleable and swappable with a few options like we've done for previous characters.
2:572 minutos y 57 segundosSo then you can see it just replied that it'll build the chosen warrior with a clean bare body, which it did right here.
3:043 minutos y 4 segundosAnd then it kept recording and then once it finished, it built up the actual items for
3:103 minutos y 10 segundosit as well, set up some animations for it and got the character ready to kind of work in game.
Capítulo 6: Prompt 3 — cloth and motion
3:173 minutos y 17 segundosOnce it worked in game, it still needed a decent amount of work. That's why that was only prompt number two. The next thing was to deal with some of the issues. One of them being cloth.
3:263 minutos y 26 segundosI wanted to have nice-looking cloth on there. so you could see how to set that up with some chains and other stuff.
3:323 minutos y 32 segundosAnd what I found in my experimenting so far is that just using Magica Cloth 2 in Unity seems to do a good job. I still haven't tried in Unreal to see what it's like in there.
3:423 minutos y 42 segundosSo I'm going to do some more experimenting and maybe try a couple other options in Unity If anybody's got any suggestions, I think just drop them in the comments.
3:553 minutos y 55 segundosseemed to work pretty well. It was able to set up the cloth, build it out in a way that it would work just fine.
4:024 minutos y 2 segundosAnd now it actually just animates and moves around.
4:054 minutos y 5 segundosYou should be able to see it like this assuming my editor is doing its job.
4:114 minutos y 11 segundosBut when it's running through this process with that diagnosing bugs.
Capítulo 7: Find and check the eye problem
4:154 minutos y 15 segundosIt also found some things like this eye issue, diagnosed it, figured out what was wrong with it and then automatically fixed it.
4:234 minutos y 23 segundosWasn't something that I had to really tell it to do, just kind of found that on its own. But it finds a lot of things on its own.
4:294 minutos y 29 segundosSometimes it doesn't, though, and I'll go back and tell it and just look in between each one of these steps and see if I notice anything and then call it out.
Capítulo 8: Prompt 4 — build a working staff
4:374 minutos y 37 segundosOnce the character was working in-game, though, the next step was to get the weapon working.
4:414 minutos y 41 segundosAnd I wanted the weapon to work like Teal'c's weapon in Stargate, so you kind of pull it, aim it, and blast.
4:474 minutos y 47 segundosHe still holds it funny and I'm trying to decide if I want to adjust that so he doesn't hold it out like this and kind of holds it more two-handed.
4:544 minutos y 54 segundosI also have him holding a shield, so still trying to decide exactly how I want that to work. But the weapon wasn't actually done with an external tool.
5:025 minutos y 2 segundosIt was all done in Blender, and I didn't set up Blender myself.
Capítulo 9: Artist and developer responsibilities
5:065 minutos y 6 segundosThe way that this is set up, there's an actual artist agent for this game that only works on art for the game and it's responsible for its own environment, doing everything
5:145 minutos y 14 segundosin its own sandbox and setting up all of its own tools.
5:175 minutos y 17 segundosSo it's doing that all on its own and it's got some experience doing lots of art and building up these processes.
5:245 minutos y 24 segundosOnce the weapon was done though, it needed to be in-game and start shooting.
5:285 minutos y 28 segundosSo I told it to set that up and make it start blasting stuff and record a couple of videos.
5:335 minutos y 33 segundosAnd now it works as an actual weapon that we can use in-game once the developer hooked up the actual combat part of it.
5:395 minutos y 39 segundos, came back and then asked it to just check the status of the videos and the
Capítulo 10: Prompt 5 — create more variation
5:495 minutos y 49 segundosintegration and then do some variations because I know it was in game and it was ready for one thing but it wasn't too much. I'd seen versions where it was wearing multiple sets of armor.
5:595 minutos y 59 segundosSo I had multiple sets of armor and blend shapes, so that we could have some variation and the muscle size and the body on the face so that everybody didn't look exactly the same.
Capítulo 11: Try the full-body customizer
6:106 minutos y 10 segundosBlend shapes are an amazing feature to add into character setups so that you can have a good amount of variety for a very low cost. It also lets you do character creators.
6:186 minutos y 18 segundosThere is absolutely no reason not to have it add them in here.
6:236 minutos y 23 segundosIf you want to do a character customization system, use the blend shapes and you've got your sliders already just kind of automatically working. It'll hook it all up for you.
6:326 minutos y 32 segundosof variation on the equipment and the guys so that they could have different ranks or whatever and be different tiers of difficulty.
6:396 minutos y 39 segundos. That was relatively quick and they came out I think pretty nice. At least I like them. I still think I want to work on the shoulders a little bit
6:466 minutos y 46 segundosmore and maybe change out some of the arm stuff. But overall I think that they're a decent looking character.
Capítulo 12: Prompt 6 — magnetic boots and alien armour
6:536 minutos y 53 segundosThere's one thing I wanted to add still which was mag boots. So I wanted these guys to be able to walk on the walls.
6:596 minutos y 59 segundos. They seemed like these big beefy heavy guys that could just like walk on the outside of the space station and blow stuff up or like stick down and you
7:087 minutos y 8 segundosknow run up a wall or something. And I thought it'd be a cool feature for the player to be able to have too and for the player to be able to take these guys over and run them up the walls and stuff.
7:177 minutos y 17 segundosAnd you can see the actual prompt it says that I said that those three plus some more alien dramatic sci-fi ones would be good after looking at these concepts here.
7:287 minutos y 28 segundosAnd let's get some good variety for them.
7:307 minutos y 30 segundosCan you add some mag boots as an option that lets them walk on walls, ceilings, et cetera too. And that's it. Now they're all in.
7:387 minutos y 38 segundosYou can see them walking around.
7:397 minutos y 39 segundosthis cost them. I don't know whatever it says up here. Couple cents though. It was really cheap and it was a couple hours of it running in the background while other stuff is going on.
Capítulo 13: Costs, setup and what actually happened
7:517 minutos y 51 segundosIt wasn't even home through most of it. So check it out.
7:547 minutos y 54 segundosIf you haven't tried this process yet, it's just Opus 5.5, the setting the second highest one, don't go all the way to Ultracode.
8:038 minutos y 3 segundosUsing the Tripo you can just use it on the free version with the free credits is more than enough. This was 55 credits. One generation.
8:108 minutos y 10 segundosLet the AI run it. It seems to do a drastically better job of running it than I do. much better result.
8:228 minutos y 22 segundosAnd it all comes out great. If you want to download these, just check down below And if you want to see more stuff like this, you got other random questions, drop them in the comments and I'll see if I can make a video about it.
8:328 minutos y 32 segundos. But oh, like subscribe all that stuff. Whatever. Finally. Someone else can carry the heavy stuff.
Capítulo 14: Character cameo and supporter thanks

