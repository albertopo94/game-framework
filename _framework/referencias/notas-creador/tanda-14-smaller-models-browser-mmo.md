0:00
You don't really need the state-of-the-art models in order
0:03
to get really good results.
0:04
Hey guys, what you see here on this screen is a massive multiplayer game
0:09
that I built, I'm trying to chase this guy who's trying to run away
0:13
from me and I have to find him.
0:14
So this is actually a fully multiplayer game, and you will see
0:17
that, the entire game is synchronized.
0:19
All right?
0:20
And let me just show you another game that I've been working it
0:23
was really inspired by your Stardew Valley, Animal Crossing style games.
0:27
you can, plant seeds, wait for them to grow, you can speak
0:31
to the NPCs, you have quests.
0:33
Now, the key thing that I wanted to talk to you about for both of these games that
0:36
you see over here is that I did not use state-of-the-art models to build these.
0:41
In fact, I actually used, smaller variants of the models from Anthropic and OpenAI,
0:46
namely Claude Haiku 5.5 and GPT-6.1-Sol.
0:50
Both of these games were just built over the past week, and so you shouldn't
0:53
see not having access to the sl- latest state-of-the-art models or the highest
0:57
tiers and subscription plans as a blocker for you to get going in game development.
1:02
So in today's video, I'll be talking you through how I built both of these
1:05
games using GPT-6.1-Sol, as well as Claude Haiku 5.5, which is a much smaller
1:12
and cheaper model compared to Sol.
1:14
So if you ever wanted to know the process that you can take to build
1:16
games such as these or other games that are in your head without needing
1:20
to rely on the state-of-the-art models all the time, this video is for you.
GPT 6.1 Sol - Cozy Farm Gam
1:24
All right, so I'm gonna talk to you about how I built this game, over here, and you
1:29
can see that this game is very inspired by Animal Crossing, Stardew Valley.
1:35
And the goal that I wanted to do over here was to build, not just the
1:39
visuals, what I'm trying to really do here is to create games that not
1:44
only just look good as a technical demonstration of the techniques, but also
1:47
to be able to have, interesting mechanics and a story and a narrative that brings
1:52
some kind of progression into the game.
1:54
So as you can see here, the goal here is to continue to earn enough money so
1:59
that you can eventually actually upgrade your house that you see over here.
2:03
I'm actually really happy with how this turned out.
2:05
You can see that the world, has a very nice aesthetic style.
2:08
the models and everything are all put in quite nicely, and you can see that
2:12
it is fairly sophisticated as well.
2:13
I can chop down trees, I can continue growing different crops, it's
2:17
also optimized for mobile devices.
2:19
So you can see here, I'm just pressing so that I can walk everywhere, and
2:22
you will see that the interaction mechanisms is very deliberate here
2:25
as well, because I want this to be something that you can play with just
2:28
one finger, on your mobile phone without having to use lots of different buttons.
2:32
Because I'm seeing that a lot of browser-based games, a lot of people are
2:35
playing on mobile, and being able to very easily have these kinds of interaction
2:39
modes is quite important for me.
Model Stack and Costs
2:40
this game that was built using GPT-6 .1 sol.
2:45
And let's just start off with the model usage that you see over here.
2:48
You can see here I'm using both Codex and Claude Code.
2:50
And what happened was that I actually built most of the things, that you see
2:54
over here until it was a complete game, and then I used, one of the Claude models
2:57
to help to expand on some of the quest.
3:00
But the bulk of it was done by Codex, and you can see here it cost me a
3:03
total of $89 just using API pricing.
3:05
and you can see the breakdown over here, and I made use of several subagents.
3:08
And I'll talk to you about what I use the different subagents
3:10
for and the reason why.
3:11
So even though this is the total API cost, actually I would say that if you just
3:14
focus on the pure game-related things, it was about $90 in API cost, whi- which is
3:20
really good for how far I managed to get.
3:22
Okay?
3:22
So let me just jump back into the game over here.
3:24
So I think the key thing to highlight is the process that I
3:26
went about trying to fulfill this.
Rust WASM WebGPU Setup
3:28
And let me just show you the prompt, that I use over here.
3:31
I did start off with a starting template which I'm starting to use for
3:34
all my projects, and the main thing is that the starting tem- template,
3:38
as you can see, is very basic.
3:39
It just has a bunch of boilerplate code because I'm using Rust, WASM,
3:42
and WebGPU/WebGL so that it can run on the web and on mobile devices.
3:46
And if you've seen past few videos, this is what I've been doing.
3:49
It just gives you great performance, it works on multiple different platforms,
3:52
and effectively works very well.
3:54
And you will see that for this other game that I'll be talking about right after
3:56
this, it uses the exact same architecture.
3:59
And the great thing about this is that, as you can see, this has, 200 NPCs running,
4:03
and then the player is also able to go in.
4:05
I can spin the camera around.
4:06
You can see this running fully at 120 FPS right now, and r- you will
4:09
see similar performance running in the online version as well.
2D Sprites in 3D
4:13
Now, the other thing that you will notice in both of these games is that
4:16
even though it's a 3D environment, as you can see over here, the
4:19
characters are actually game sprites.
4:21
So these are 2D sprites that are, put in against a 3D environment, and it
4:26
can give you a really nice aesthetic.
4:28
It's something that I really enjoy because, as you can see over
4:30
here, when you blend in the 3D environments with these 2D sprites,
4:34
it gives you a particular look.
4:37
So I think some games that have this style is a little bit like Final
4:40
Fantasy Tactics or Octopath Traveler,
4:42
I think Xenogears is also another one, if you are familiar with
4:45
that from the PlayStation days.
Spriterrific Sprite Pipeline
4:46
Okay.
4:46
So very quickly for this one, all of these sprites that you see here were
4:50
made using a tool called Spriterrific, which is a tool that I built in order
4:55
to create game-ready sprites very easily using text prompts, and it
4:59
works with any agent harness that you want, whether it's Cursor, Claude
5:02
Code, Codex, Grok Build, whatever.
5:04
Now, the problem that you have with even some of the state-of-the-art models
5:06
right now, if you haven't tried them yourself, you will know that they do
5:09
struggle with 2D sprites quite a lot of times, especially in walk cycles,
5:14
and Spriterrific is a tool that I built, in order to solve this problem.
5:17
And you can see a bunch of different, games that I've made using Spriterrific,
5:21
whether it's a beat 'em up game, whether it's a platformer, whether
5:24
it's a point-and-click adventure game, and these are some of the other
5:26
examples of other users that have made use of Spriterrific as well.
5:30
we've got thousands of users and almost 8,000 animations that have been
5:33
generated, and the idea that I wanted to have is that something that allows
5:36
you to really easily get game sprites into your game, whether it's a 2D game,
5:40
or 3D game, or a 2.5D game that you're seeing over here just by prompting.
5:44
And the approach that I take is that when I build my own games, I use a
5:46
process called dogfooding, which is effectively using your own tools, to
5:50
make sure that they work correctly.
5:51
I think it's really important if you're building a tool or something that you
5:54
are letting others use, that you should be using it for yourself as well.
5:57
So this is why you can see that the opening prompt that I used to
6:00
make this game was specifically, to create a tech demo using 2D sprites
6:05
within a 3D environment, and then I can say, I will dogfood Spriterrific
6:08
through its public version.
6:09
So that's the version that, everybody can have access to.
6:11
And then I said I want to use the WASM WebGPU demo with WebGL fallback.
6:16
Now, this is exactly what I told you before.
6:18
It's been what I've been using for pretty much all my games that you see
6:21
here on my Wave Dash profile, bar this one which was made using Unity, and I
6:25
really enjoy this set of tools because in some sense you don't really need
6:28
to rely on frameworks, and you have full control and it's very performant.
Mockups and Floor Plans
6:32
So check my other videos where I actually outline some pros and cons on why you
6:35
want to take this approach, Now, with every project, I always encourage
6:38
you to focus on generating mockups.
6:41
So I can say, let's generate using GPT Images 2.5, and if you're using Codex,
6:45
you get image generation out of the box.
6:47
And I said, generate four mockups that would help set
6:50
the creative and art direction.
6:51
And in fact, at one point it actually tried to make use of fal.ai which
6:55
is something that I also use.
6:56
But I said, "Hey, wait a minute, silly, you have to use your own image
6:58
generation capabilities in Codex."
6:59
So you can see here it began to generate lots of different art styles, for me, and
7:03
a lot of them resonated quite well with me, but it wasn't quite hitting home.
7:07
And then I said, I want something, cozy farm and town-ish.
7:11
And then it came up with these sets and I said, "Hey, this is starting to
7:16
look in the direction that I want." So you can see these are the two
7:19
ones that I thought really fit the vibe that I was going for very well.
7:22
And you can see here I'm starting to do a lot of typos because I
7:24
was actually sending a lot of these commands on my mobile phone.
7:28
So one of the things that I do is that I use Termius, and I actually
7:31
make use of my phone to connect to my running instances in order to
7:35
build the games when I'm on the go.
7:36
And you can see lots of typos over here, but it seems to
7:38
understand what I was saying.
7:39
So I want to generate parallel floor plans and the terrain, for
7:42
the environment and the props.
7:43
when I'm trying to generate the environment, I always ask it to generate
7:48
floor plans, so that it will actually be able to lay out a level design
7:52
As you can see with this game, this is exactly how it turned
7:55
out, the way that it's laid out.
7:56
It has the farm on the left and then all the other houses and the NPCs on
7:59
the right, and a lot of this is down to the fact that this was generated first.
8:04
And I always encourage you to use floor plans, top-down views, and alternate
8:07
views in order to ensure that you end up with games that are not only nice
8:11
to look at, but actually can play well
8:13
And then you can see here it generated all the different props that would be
8:15
needed, and then finally it generated the reference image for the character
8:21
that would go along with these vibes.
8:23
And like I said, you can look at this, see the game character
8:25
over here matches it perfectly.
8:27
But I'll talk a little bit about that later.
Parallel Subagents Workflow
8:29
So now that we have the floor plans, props, and the, characters that we want,
8:34
this is where I make use of sub-agents to do things in parallel, because you do not
8:38
need to be building things one by one.
8:41
These are all separate steps, 3D, 2D, environments, et cetera.
8:45
So you can see here, build the level props and environment in Blender
8:48
with a pipeline that we know.
8:49
This is the existing pipeline that I use for all my games.
8:52
And then integrate it into the scene, So you can see that it was able to
8:55
create the level within Blender, which I'm, and all of the props that
8:58
can be exported from Blender as well.
9:00
So I'm just gonna show it to you over here.
9:01
You can see this is the final level that it did within Blender, and the
9:05
way that it was done matches the floor plans that we saw earlier.
9:08
And then all these are exported out into the game individually
9:11
such that it looks and runs right, and also, works in mobile as well.
9:16
And as you can see within the game, looks great, and functions perfectly
9:20
within the world and then I say, in parallel, use Spriterrific to generate
9:23
the character that we want with walk, run, idle, and interact animations.
9:27
Now, this is the thing that I wanted to highlight about Spriterrific, is
9:29
that this is all you need to do in order for it to generate all of the
9:33
animations that you see in the game.
9:35
You don't need to go any more detailed than that.
9:37
you can just give it a high level instruction of what you want, and
9:40
it will go ahead and build it.
9:42
And just to show it to you here, this is the quick start of Spriterrific,
9:44
and all you need to do is just literally copy this AI prompt, paste
9:47
it into your project, make sure you have an API key, and put it into your
9:50
environment variables, and then you can just prompt your agent in this way.
9:53
Generate a character, and it will just do everything automatically for you.
9:56
this is a deliberate choice I made for Spriterrific because I didn't really like
9:58
having to go to a web interface for you to then choose what animations you want.
10:01
I just wanted to stay within my agent harness.
10:04
And as you can see here, this is the only line that I did in order
10:07
to get the animations that I wanted.
10:08
So from that one single prompt, what it does is that the skills will
10:12
automatically figure out how to prompt Spriterrific to get you what you want.
10:15
So let me just show you here.
10:17
All we started out was this reference image that was generated, and it then
10:20
was able to create different versions of the walk and the run and the planting
10:24
of seeds and watering, and all of these were just generated automatically.
Fixing Animations Fast
10:29
sometimes you might end up with an issue where this idle animation looks
10:31
right, but perhaps something about this run didn't look right, I've actually
10:34
made a bug fix as a result of that, and that's the reason why you always
10:37
have to dog food your own tools because you encounter bugs that your users
10:41
will have, and then you can fix them.
10:42
I just re-prompted it and said, "Hey, he faces the wrong way.
10:45
what's going on?" And then I said, "He has three hands at one point."
10:49
So after that, your agent will be able to prompt Spriterrific
10:51
to fix up the animations for you.
10:53
And you can see that this was done for all of the characters in the game.
10:57
So I'm just gonna run over here.
10:58
So you can see we have this, character here who gives you quests.
11:00
There's this other person who's, sweeping the floor, and then this,
11:03
grandma who is standing here, who you can talk to all of these prompts were
11:07
automatically generated by 6.1 Sol.
11:10
And ultimately, I was very happy with the results that came out of this.
11:12
So you can see it was doing a relaxed stroll.
11:14
For one of the neighbors, he had a sweeping animation.
11:17
And then if you need more animations, you can just say, " I want to be
11:21
able to have a chopping animation," and it will do it for you.
11:23
So this is the reason why I built this tool.
11:25
It's just specifically so that I'm able to very easily create characters
11:29
in 2D sprites for my games, and this is what I've been doing for
11:33
any games that require sprites.
11:34
If you wanna check it out for yourselves, it comes with free
11:35
credit, so you can check it out.
11:36
The link is in the description below.
Progression and UI Iteration
11:38
With all of these in place, I was able to get pretty much all
11:41
of the, functionality working.
11:43
I did prompt it for the analog control so they work well on mobile.
11:46
And then the only other thing that I spent time was iterating on the core,
11:49
progression that I wanted to have.
11:51
And this is where it's very useful to have a mixture of image generation,
11:55
because I said, "Create me a storyboard." So the idea here is that you start
11:58
small, you harvest, you sell, you reinvest, and then you open up rest
12:01
of the village, improve your home, and then you basically continue on.
12:04
And this is exactly, what the game does.
12:06
So you can see after that, I said, "This was really good. Let's, generate more
12:10
of the models that allows you to have bigger homes," and then to make sure
12:13
that the core game loop worked correctly.
12:15
And then once you have this baseline in place, you can go ahead and
12:18
do things like, oh, we should have more obvious progress bars.
12:20
I think we have to have something that's more in- clear that it's interactable.
12:24
And the idea here is that you can then just iterate very quickly.
12:27
and because this model is a faster model than using Astra, you're able
12:31
to iterate very quickly and then get to the state that you want.
12:33
That was pretty much what I did for this game.
12:36
I went ahead and continued adding things like the UI menu, and then I
12:39
just continued to use Spriterrific to generate more of the animations in
12:42
order to fill up the core game loop.
12:44
And what you end up over here with is now this game, which I am, almost ready to,
12:49
completely go and launch on Wave Dash.
12:51
I just have a couple more things to finish up, so stay tuned because I'll
12:54
be giving some updates on how this game performs, and hopefully more people will
12:58
get to play it and get to try it out.
13:00
And this should be releasing very shortly.
13:03
So that was how I built this game with GPT-6.1 Soul.
Claude Haiku 5.5: Haiku Harbour
13:07
The other game which I'm gonna talk to you about is this one called Haiku Harbor.
13:10
So I found out that Haiku 5.5 was released two days ago now, so I was saying I
13:14
would love to continue down this path.
13:16
So in what ways could I once again make use of a 3D environment with
13:21
2D art and then create a game?
13:23
Yes, I used a very similar process that you saw with with the farming
13:26
game, but this one was really gonna be more of a technical demonstration.
13:29
But I wanted a twist, and the twist that I really wanted to have for
13:32
this game is that I wanted it to be a multiplayer game with lots of
13:37
NPCs, running around the screen, and I wanted it to be still running at
13:40
the highest possible performance.
13:42
So for this project, I'll be focusing less on the pipeline.
13:45
I'll be showing you what I learned when I was using Haiku, which is a
13:48
much smaller and cheaper model than not just GPT-6.1 Soul, but even the Luna
13:54
models from the GPT series, which is the lowest and cheapest models from OpenAI.
13:58
And the fact that you're able to build a game like this in just a couple of hours
14:01
just from prompting and because Haiku is really fast as well, is really impressive.
14:06
Remember, this is fully multiplayer now.
14:07
You can see, oh, he's hiding in this hub over here, and there's
14:10
a little bit of a bug with this animation, which I'm about to fix.
14:12
So but I think I how it's working now, so you can see
14:14
he's running away from me here.
14:15
So if I join in now and I try to run up, you can see over here he's
14:19
running away from my other character, which is fully synchronized.
14:22
So I'm gonna chase him over here and just swap back over here.
14:24
You can see my character chasing him, and this character on
14:27
this side is, fully working.
14:28
I use something called Colyseus, to do this multiplayer, and it was very easy.
14:32
I've done other videos where I make games multiplayer using Colyseus as well.
14:36
and I highly recommend it if you're thinking of making a multiplayer game.
Haiku Costs and Prompting
14:38
Let me just show you the usage.
14:40
So for Haiku, what I found was that because it's a smaller model
14:44
it tends to not be- I get things as fast as the other models.
14:48
But the great thing is that because it's so cheap, you're able to
14:51
do lots and lots of iterations.
14:53
So you can see here the estimate of the cost over here was about $93,
14:57
which is still really cheap for what I was able to get and the number
15:00
of prompts that I did because I was really iterating on this so quickly.
15:04
I was just, like, adding multiplayer.
15:06
I was, like, improving the graphics.
15:07
I was, like, using Spriterrific, adding this character, adding that character.
15:10
Because it was so fast and so quick, I was just able to iterate on this a lot.
15:14
And for $93 to be able to get to this point, a fully multiplayer
15:16
game that is fully synchronized, that is hosted, and just works out
15:19
of the box is actually really cool.
15:21
I'm not 100% sure if I got this pricing correct, so I'll need to
15:24
double-check it because I think it might actually be a little bit cheaper.
15:27
But the ballpark figure something that's sub 100 for you to get to this point,
15:30
given the number of prompts that I used, is actually really impressive.
15:33
So with that, let me just show you the prompt that I opened up with.
15:36
And you can see here, our goal here is to build a multiplayer demo that
15:38
involves 2D sprites in a 3D world.
15:40
It needs to use th- this framework that I use, so Rust, WASM, and
15:43
WebGPU with WebGL fallback, and then Spriterrific for 2D sprites.
15:46
I said it's a massive multiplayer world.
15:48
Goal is to demonstrate how we can render thousands of players synchronously
15:50
walking around in a large 2.5D environment with no visible lag or
15:54
degradation, optimized for control, optimized for portrait mode, et cetera.
15:57
And then I then went through, the same process that you can see over here.
16:00
Ask it to do a bunch of different mock-ups, and you can see that this
16:03
is the one that I got inspired for.
16:05
So then I basically said I wanted to use something between this harbor
16:08
town and this city plaza, which is exactly what this game ended up having.
16:13
So you can see here, it is a harbor town, and then there is actually
16:16
a plaza on the other side as well, so you can see over here.
16:18
This world is actually fairly big.
16:20
Right now it has about, I think, 200 to 250 NPCs, but I'm quite sure
16:25
that it will work even up to 1,000.
16:27
But it might make the game very busy.
World Building and Characters
16:29
So unfortunately, I didn't do my usual process of journeying
16:32
with every single prompt.
16:33
It was quite a lot of long set of prompts because like I said, Haiku doesn't
16:36
get things as right the first time.
16:37
But let me just show you, the world that it was able to build in
16:40
Blender, and this is fairly decent.
16:42
I would say it wouldn't compare immediately off the bat to something
16:45
from Sol- For a small model like Haiku, being able to build this up
16:51
and then bring it into the game thing and integrating multiplayer as well as
16:53
the 2D sprites was really impressive.
16:56
Now, I, now I wouldn't hide the fact that this took a lot more prompts
16:59
than it would have perhaps if you were using a much more powerful model.
17:03
But I was trying to do quite a lot of things.
17:05
I was iterating on this like crazy.
17:07
I was saying I'd like to want to improve it.
17:08
And towards the end, I was, quite happy with the result.
17:12
I also made use of Spriterrific to create a whole bunch of different characters.
17:15
And like I said, I didn't really, need to do anything special.
17:18
I just said, "Just generate me a bunch of different characters that will fit the
17:21
game." And these prompts that you see here were all generated automatically by Haiku.
17:25
And the idea here is that with the skills of Spriterrific,
17:28
you don't need to do much more.
17:30
You can just basically say, "I just want this number of characters, I want this
17:32
number of animations." And I was able to get all of these different sprites
17:36
that you see over here, different characters, all into the game, and,
17:38
they all just needed a single prompt.
17:39
And that's not just the NPCs over here.
17:41
So you can see if I just run up to the stage, all these band members,
17:45
one is a singer, one's playing the drums, one's playing the accordion,
17:47
all of these were all generated, and I didn't really have to do too much.
17:50
And the idea that I actually initially had was to allow people
17:52
to just generate more characters to fill up this world, but I haven't
17:55
actually gotten around to doing it.
Live Chat and Hosting
17:56
And right now, as I'm recording this, you can see there is another
17:59
live player playing the game.
18:00
and just to show you again It has full chat functionality as
18:03
well, and it's fully synchronized.
18:05
So that's really cool.
18:05
in fact, I was having a conversation with, some of the people on X or
18:08
Twitter in the game itself, and it was actually quite surreal.
18:10
So let me just see if I can chat with this person.
18:12
Hello there, sunnyotter665.
18:15
Have you found the guy?
18:16
And you can see this is all real-time multiplayer, and being able to build
18:20
this entire game with characters, with character selection in Haiku
18:23
was actually really cool as well.
18:25
And just a quick word on Colyseus, all I did was to say to, Haiku,
18:29
make use of Colyseus to make this a real-time multiplayer, and then
18:32
I'm using Railway to self-host it.
18:34
So there are two ways you can do it.
18:35
You can deploy it on their cloud, or because it is actually open
18:38
source, you can actually go ahead and run and self-host this yourself.
18:42
So that's exactly what I did.
18:44
I just said that, "Use Colyseus for multiplayer, make it synchronous,"
18:46
and I just prompted my way to the point where it was running well.
Multiplayer Optimization Tips
18:50
Now, one of the things that you will need to focus on the fact that
18:53
when you make a multiplayer game with all of these movements of these
18:55
different characters, you do need to do a bunch of different optimization.
18:58
So there are a lot of different techniques that you can do.
19:00
I want to go into details over here, but basically you can just talk to
19:03
your AI agent and say, "Hey, there's a bit of rubber banding, or there's
19:07
a bit of, jittering, or there's a bit of lag," especially with the controls.
19:10
So a couple of things that you want to do, which I'll share right now, is that
19:12
you want to have client-side prediction.
19:14
Client-side prediction means that when a when a player press left or
19:16
right, you predict, that they're going to definitely move in that
19:19
direction even before the server confirms that the position is there.
19:23
Because if you wait for your position to be sent to the server and then back
19:26
in order for all of your players to see in the same position, you see a lot of
19:28
lag or you see a lot of rubber banding.
19:30
The other thing that you can do is also with, the movement of the NPCs.
19:34
There are a lot of optimization techniques that you can do.
19:36
So you can say, use a single seed such that everybody sees the same
19:39
simulation, or you can say for each of these NPCs send, a much smaller
19:43
representation of where their position is.
19:46
So I want to go into a lot of details.
19:47
If you'd like to learn more about multiplayer game development, do
19:51
let me know and I might do a whole dedicated video on how you might
19:53
make use of Colyseus or any other multiplayer framework in order to
19:56
get lots of characters on screen.
Wrap Up and Next Video
19:58
All right.
19:58
I hope you've seen how you don't necessarily need to be using your Fables
20:02
or your Opuses or your Astras to be building games, and not just games that
20:06
are tech demos like you see for this one, but games that can have a full experience
20:10
for the user, like cut scenes and tutorial- and a full game loop, I think
20:15
that there is really no barrier to be able to make these sort of games right now.
20:19
And like I said, my goal here is to not just build these games just to demonstrate
20:23
the capabilities, but to actually put them on the web, like I've been doing
20:25
right now, so that I can actually see how real players are enjoying them, and
20:30
how I can continue to make use of AI to build more fun and compelling games
20:33
that people want to come back and enjoy.
20:35
So if you found it helpful or informative in any way, give this video a like,
20:39
hit that subscribe button, and don't forget to turn on notifications so
20:41
that you'll always be the first to know when new content like this drops.
20:44
Now, if you haven't seen my other video where I actually walk through how I
20:48
actually made use of Sonnet 5.5, which is a mid-tier model between Haiku and Opus,
20:55
to build a game, but to launch it and get lots of different players playing as well.
21:00
in this game, you grab hold of patrons and try to toss them
21:03
out before the time runs out.
21:05
And all of the things that you see on the screen today, including the
21:08
physics, the, animations, the models, and everything, was done using Sonnet 5.5.
21:14
And it just demonstrates once again the power of the models
21:17
that you have right now.
21:18
You can take a crazy idea, build it, and then get it into the hands of
21:21
people in a short amount of time.
21:23
since I launched it, I had about 110 players play it this month, which is
21:27
really cool, and I think that's a really nice thing about building games, in this
21:31
day and age, is that you can get it out into the players' hands very quickly.
21:35
So if you want to learn more about that, you definitely wanna
21:37
check out this video over here.
21:39
All right?
21:39
So till next time, I'll see ya.
