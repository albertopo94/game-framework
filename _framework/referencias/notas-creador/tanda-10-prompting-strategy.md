Intro
0:00
In this video, I will show you my
0:01
step-by-step a toz process for building
0:03
the games you see on this channel. All
0:06
with only the AI models. No game
0:08
engines, no MCPS, no outside tools, just
0:11
a strategic prompting strategy. I put
0:14
this complete guide linked in the
0:16
description so you can access it at any
0:17
time. All I ask is that you give the
0:19
video a like if you found it to be
0:20
helpful and consider subscribing for
0:22
more content like this. Okay, so my
My 7-step process
0:25
entire process consists of seven steps.
0:28
First, we're going to write our initial
0:29
prompt. We're going to give the model a
0:31
target. We're going to let it run. We're
0:33
going to play it. We're going to score
0:34
it and revise it. We're going to save
0:36
it. And we're going to ship it. Now, 3,
0:38
four, and five. This is where the magic
0:40
happens. And we'll break this down in
0:41
detail below, but essentially, this is
0:43
where you are letting your model run on
0:45
a loop until it hits the goal that
0:47
you're after. I do this by a simple
0:49
numerical score. So I always tell it
0:51
that it needs to reach a 9 out of 10
0:54
based on the example that I have given
0:57
it here in my target. So here for our
1:00
Opus Ring game, we can see that this was
1:02
a 1 out of 10. We improved to a two,
1:05
eventually got to a four. And then this
1:07
is the shipped build that you actually
1:09
can play for free in my arcade. Now I do
1:12
this numerical scoring for both the
1:14
entire build as a whole and for specific
1:16
aspects. But let's not get ahead of
1:18
ourselves. Let's start with the initial
Step 1: Write the prompt
1:21
prompt. This is where most people set
1:23
themselves up for failure because they
1:26
overengineer and over complicate their
1:28
first prompt. I had an agent analyze my
1:32
last 188 game builds and on average my
1:36
opening prompt is just 44 words. I'm
1:39
using very simple language just like I
1:42
would brief a normal person to start a
1:45
task. For example, here's my opening
1:48
prompt for my Hogwarts Legacy of Magic
1:51
game. I have it broken down into six
1:54
different areas. So, first I'm
1:55
describing the fantasy that I wanted to
1:57
build, right? Then we get into the
2:00
description of what can actually be
2:03
done, what things we need to make sure
2:05
are included in regards to gameplay
2:07
elements, features, etc. [music]
2:10
Then I set the bar for how good I want
2:12
it to be. basically just using words
2:15
like it needs to feel incredible. I want
2:18
all the details. I want the character
2:20
models and everything to just be
2:22
absolutely exceptional. Next, I allow it
2:26
to use any of the skills from my custom
2:28
skill library. And we'll get into that
2:30
because this is honestly one of the most
2:32
impactful things that you can start to
2:33
do using skills, whether you get them
2:35
from someone else or your own to
2:37
expedite these builds and maintain
2:39
quality standard. Next, I let it know
2:42
how long I want it to run on this
2:44
initial loop. Whether that's a specific
2:46
time frame for a comparison build or
2:49
something generic like I want you to run
2:51
on a loop until the result is absolutely
2:53
mind-blowing. Next, I try to give it a
2:56
list of priorities. So, the things that
2:58
I really want it to focus on. In this
3:00
case, we really need to focus on
3:01
gameplay, graphics, scale, details, etc.
3:05
All right. Now, that prompt I just
3:06
showed you was for one of my most
The 6 types of prompts I use
3:08
ambitious builds yet. But not every
3:10
prompt has to look the same. In fact,
3:12
this is where a lot of people go wrong.
3:14
They use the same engineering structure
3:15
and strategy for every single project. I
3:18
found that most of my builds fall into
3:20
one of the following categories. The
3:21
oneliner prompt. This can be used to say
3:24
something like, "Build me a game similar
3:27
to Star Wars Rogue Squadron." Right? And
3:30
you can send that off and just see what
3:32
kind of results you get. These prompts
3:33
are fun to test new models with, but
3:35
they're typically not the prompt you'd
3:37
go to if you're trying to build
3:39
something substantial. Now, next we have
3:41
the oneshot prompt. This is my go-to
3:44
when a new model drops for quickly
3:46
comparing models. First of all, I just
3:49
break it down into three short
3:51
paragraphs. The first one is literally
3:53
letting it know, you have one shot to
3:55
build this, so you better put your best
3:56
foot forward. Sometimes I even include,
3:58
I'm going to be comparing you against X
4:01
competitor model, right?
4:03
Then I let it know what I'm expecting.
4:05
So in this case for Spider-Man, the
4:06
models need to look incredible. The city
4:08
needs to look incredible. It should feel
4:10
detailed. I should obviously be able to
4:12
swing from building to building, fight
4:14
bad guys, etc. And then for these one
4:17
shots, I like to close it with this
4:19
should be an absolute showcase of your
4:21
capabilities of a model. And of course,
4:24
you have to put in [music] don't
4:26
disappoint me. Next, we have the clone
4:28
prompt. I actually ran this last night.
4:31
I had it create a clone of the mobile
4:33
game Wii Rule. So, typically I will
4:35
insert like the Wikipedia link or maybe
4:38
a Steam page or whatever it is uh just
4:41
to give it some sort of idea of what
4:45
it's supposed to replicate. So, for this
4:47
specific prompt, I told it to loop for 6
4:49
hours without stopping. Build a one for
4:51
one clone of Wii Rule. Should be a 9 out
4:53
of 10 in closeness to the original game.
4:55
So, there's that numerical score I'd
4:57
mentioned earlier. I repeat, do not stop
4:59
early. go for minimum of 6 hours. I want
5:01
to be impressed in the morning. Looks
5:03
exactly like the game. And couple quick
5:05
things. You'll notice I keep repeating
5:07
do not stop cuz sometimes these models
5:09
will choose to stop early unless you
5:11
really hammer that. And one thing I also
5:13
included do not optimize for mobile.
5:16
Since I'm building this for a browser,
5:18
what I found is that especially if you
5:20
try to clone or replicate a mobile game,
5:22
these models will try to spend a ton of
5:25
time and tokens optimizing for mobile.
5:28
So, I just say it loud and clear. This
5:30
is not for mobile. Don't do it. So, next
5:34
we have the vision with a list. And this
5:36
is where you start to get into the more
5:38
robust games. So, in this case, I want
5:41
you to recreate iconic locations from
5:43
Lord of the Rings in insane detail. They
5:45
should be highly detailed 3D renderings.
5:47
And here I lay out the vision. My vision
5:49
is there's a map of Middle Earth that
5:51
looks gorgeous. We can click on certain
5:53
locations and it brings us to those
5:54
locations where we see detailed 3D
5:56
models that we can actually explore. And
5:58
then I list out specific models or
6:01
locations I want to see. It should be
6:03
massively detailed. Absolutely
6:05
mind-blowing. I find that hammering that
6:08
you really want detail is important. And
6:10
for some reason, I use the word
6:12
mindblowing all the time. It works for
6:14
me. If it ain't broke, don't fix it.
6:16
Next, we have my favorite one, the
6:18
overnight prompt. I love setting a
6:21
prompt and waking up in the morning to
6:22
something incredible. So, this looks
6:24
something like, I want you to run on a
6:27
loop until X time or for X amount of
6:30
time. Uh, and now if you are trying to
6:34
maximize your tokens, right? You're
6:36
trying to token max and let's say your
6:38
reset is at midnight the following
6:40
morning and it's 8:00 p.m. the night
6:44
before. you could tell it run until
6:46
midnight or until you run out of usage
6:48
because you're just trying to token max
6:50
for your usage reset. Uh but unless
6:52
that's the case, I would probably omit
6:54
the run out of tokens in that time. I
6:56
want you to build and then you go
6:57
through what your expectation is. And
7:00
then we have the upgrade pass here. So
7:03
we can see my Batman game, the before
7:06
and then the after three additional
7:08
hours of upgrades. It's subtle, but it
7:11
makes a big impact, right? So overall,
7:13
the lighting looks better, character
7:14
models look better. So we're going to
7:16
use this for when a game already exists,
7:19
and it needs to be better. Now, you can
7:22
come in, you can just copy all these.
7:24
There's also a section at the very
7:25
bottom of this guide, uh, where I
7:28
actually have some interactive tools to
7:29
give you prompt structures completely
7:31
free. So, I found that there are some
7:35
phrases and words that really pull their
Words that work (and what to leave out)
7:37
weight, and then there's some things
7:38
that you probably want to leave out of
7:40
your prompts. So words that pull their
7:42
weight should be it should be able to.
7:44
Right? This is turning a description
7:45
into a list of things that absolutely
7:47
have to work. One for one and
7:50
indistinguishable. Uh this is literally
7:52
saying this needs to be a carbon copy.
7:54
I'm not looking for that three out of 10
7:56
somewhat recognizable. It needs to be a
7:58
nine out of 10 at minimum. A fan should
8:02
say, right? So when somebody plays this,
8:05
they should say X or they should feel X.
8:08
Uh, typically I will literally just say
8:10
when somebody sees this or plays this,
8:12
they should be thinking, "Holy cow, I
8:15
can't believe AI built that." I always
8:17
let it know that this should showcase
8:19
what you can do. Right? This is your
8:22
first impression as a model. Put your
8:25
best foot forward. And this is just for
8:28
me personally. Do not invert controls.
8:30
Anytime there's any kind of flying game,
8:32
it always inverts controls. And that's
8:34
just a skill issue for me. But you can
8:36
include those small quality of life
8:38
things. Now I try to leave out things
8:41
like how to build it. I don't tell it
8:42
what to do. I trust it to do its thing.
8:46
A full design document. Now in previous
8:49
videos I actually had talked about using
8:52
these and I still think that they are
8:55
useful but not as crucial as they were
8:58
for older models. For previous models,
9:01
the design document was a surefire way
9:03
to make sure that you hit your target.
9:06
But I'm finding that these newer,
9:07
smarter models do not require them to
9:10
get the same outputs as long as you
9:12
follow the structures I'm breaking down
9:13
here. And I absolutely leave out may I
9:17
go for hard, it should do this or it
9:19
should not do that. No. Give it clear
9:22
direction. All right. Next, let's talk
9:25
about actually setting the quality bar.
9:27
This is probably the most important
Step 2: Give it a target
9:30
thing for getting the right outputs. And
9:33
the rule of thumb here is that pictures
9:35
beat paragraphs and screen recordings
9:38
beat them both. So words like gorgeous
9:41
and mind-blowing and long typed out
9:43
descriptions can do a great job of
9:45
setting the mood, but they don't do a
9:47
great job of setting the quality bar. A
9:50
reference is what you need here. So
9:51
there's four kinds of references I use.
9:54
The first is a screen recording. This is
9:56
my go-to if I can. It just does the best
10:00
job of actually showcasing exactly what
10:03
you're talking about. The next is a
10:05
target image. So, if there's something
10:07
very specific, I will literally just
10:09
screenshot that thing. For example, when
10:11
I was doing my Hogwarts build, it kept
10:14
having an issue where the character
10:16
model's leg sort of turned into the
10:18
broomstick. So, I just screenshotted
10:20
that exact part, not the whole image,
10:22
but just that exact thing. And then I
10:25
told it, here's what's broken with the
10:27
model. Fix this one thing. And the next
10:30
result was it was completely fixed. So
10:33
that's just getting very specific. A
10:36
screenshot next to my mockup. So if the
10:39
look is off, I'm going to send it two
10:41
images, what it made and a mockup of the
10:44
quality that I would like to see. So
10:46
I'll use things like actual images or
10:49
references for this. Uh, I will use GPT
10:52
image gen to build realistic quality
10:55
mock-ups. For example, I'll let it know,
10:57
I'm building an Elden Ring copy called
11:00
Opus Ring using Opus 5.5. We can't seem
11:03
to nail the graphical style. I want you
11:06
to create a mockup of what you think is
11:08
the highest quality level of graphics
11:11
that this model can hit. Keep it
11:14
realistic, right? And then I'll give it
11:16
that and I'll say, "Hey, see if you can
11:18
hit this bar." And that works really
11:19
well. Research and real plans. So for
11:22
real places, for example, if I'm saying,
11:24
"Hey, rebuild a one for one model of New
11:27
York City, then I will tell it to go and
11:29
actually look at the charts of New York
11:32
City." In this example, I had it build
11:35
my Scott simulator. So I actually gave
11:38
it the blueprints of the Dunder Mifflin
11:41
office to build out. So, a great example
11:44
in my Hogwarts Legacy of Magic game, I
11:47
kept telling it to build the castle at
11:49
scale, but it was just way too small.
11:52
So, I got really literal with it. I
11:54
said, "First, get the layout blueprints
11:56
of Hogwarts. Rebuild it room by room at
12:01
scale with detail loop for as long as it
12:04
takes to do that." And then I told it
12:07
once this is complete and looks good,
12:10
then we'll move on to surrounding areas.
12:12
The issue is sometimes these models will
12:14
try to be building Hogwarts, Hogsme,
12:16
Hagrid's hut, the Quidditch pitch, the
12:18
Quidditch miniame, everything all at the
12:20
same time. We need them to dial in and
12:23
put their energy on one thing and give
12:24
them a specific reference to replicate.
12:27
And that's where you really start to get
12:29
incredible builds at scale. All right.
12:32
Next, tell it when you want it to stop.
12:35
And we've hinted at this a few times,
Step 3: Let it run
12:37
but you'll see a lot of my prompts say
12:38
run for X amount of hours or run on a
12:42
loop until you accomplish Y. You see, by
12:46
default, these models will stop as soon
12:48
as it has something that runs. And that
12:50
first version is almost never a good
12:53
version. This is why people will comment
12:55
and say, "Why do your oneshot prompts
12:57
look better than my 10th revision?" It's
13:00
because I specifically framed my one
13:03
shot to run until it met a specific
13:07
goal. Now, this isn't always the case.
13:10
If I'm trying to do a raw oneshot
13:12
comparison, I will be more generic, but
13:15
for the start of a long build like
13:18
Hogwarts or Opus Ring, this is always
13:21
how I'm going to start off. All right,
13:23
so a couple quick things here. I talked
13:25
about this earlier. These models will
13:26
stop prematurely. If this keeps
13:28
happening, I give it this prompt. Uh,
13:30
you can come in here and copy this.
13:32
There's also kind of a bonus bedtime
13:34
prompt here. For example, with Hogwarts,
13:36
I was going to bed and I said, "Hey, I
13:37
want you to spend the whole night
13:38
working specifically on interior uh
13:41
details." Right? So, just some quick
13:44
bonuses in here that you can go ahead
13:46
and copy. And just some honest notes
13:50
here. These long runs, they use a lot of
13:52
usage. Uh, I'm on a 20x plan and I don't
13:55
have a problem with it. if I am careful
13:58
and strategic about how I prompt. But if
14:00
you are on a 5x plan, this is not going
14:04
to be super feasible for you. And
14:07
regardless of your plan, you should save
14:08
these long runs for builds that you are
14:11
serious about and really want to push. I
14:14
do not do these for most of my games.
14:17
These are reserved for specific builds
14:19
at a larger scale like Hogwarts, Darth
14:22
Maul, Opus Ring, etc. Okay, once you
14:25
have a playable build, it's time to just
14:27
go ahead and play it. And this is the
14:28
easiest and most fun part of the
Step 4: Play the build
14:30
process. Essentially, what I do is I
14:33
jump into my first build. So, for Darth
14:35
Maul, this was our first result that I
14:37
rated a 2 out of 10. And I basically was
14:41
just going through and telling it what I
14:44
liked and didn't like. And by the time
14:47
that we shipped, here's what it looked
14:49
like. For example, one of those things I
14:50
was like, "Listen, Darth Maul is on the
14:52
same team as the battle droids. Why am I
14:55
fighting battle droids?" So, for the
14:57
training area, it actually had me fight
14:58
these hologram Jedi, which made a lot
15:01
more sense. For Hogwarts here, the
15:03
initial prompt, it looked super bland.
15:06
It did not have that wow factor. By the
15:09
time we shipped it, it was massively
15:11
upgraded. So, essentially, I'm just
15:13
going through and I'm just telling it in
15:16
real time my first impressions. Hey,
15:19
this looks super dark. I'm not impressed
15:22
with the graphics. The lighting doesn't
15:25
look good. There's these blades from my
15:27
lightsaber that get stuck in the air
15:29
when I swing it. And by the end, all
15:32
that's fixed. I mean, just look at the
15:34
lighting difference. It's absolutely
15:36
astonishing. So, literally just play it,
15:38
call out what you don't like, and also
15:40
call out what you do. All right. Now,
15:42
when we are giving that feedback, what's
15:44
good, what's bad, we need to follow
Step 5: Score it and revise
15:46
these five principles. Say what's
15:48
working, which we just covered. Give it
15:50
a score. Say where it needs to land.
15:52
List two to four specific problems. Size
15:55
of the round. So, here's what this could
15:57
look like. Let's say I am trying to
15:59
improve the combat for my Darth Maul
16:02
game. I'd say something like, "The
16:04
combat feels terrible." I would rate it
16:07
a three out of 10, and it should be at a
16:10
nine. Specifically, the things that are
16:14
terrible are that when I swing my
16:16
lightsaber, the blades get stuck in the
16:18
air and don't disappear from the screen.
16:21
I'm hitting the enemy models, but no
16:23
damage is being done. The movement feels
16:25
extremely sluggish, and there's a
16:27
massive lack of variety in animations.
16:30
Every time I swing my lightsaber, it's
16:33
the same left to right animation. We
16:35
need variety.
16:38
The combat also feels extremely slow.
16:40
Again, it's at a 3 out of 10. I want you
16:43
to take the next 2 hours to work on this
16:46
exclusively and give me back a result
16:48
that scores a 9 out of 10. Right? So,
16:51
here we can see as I'm building Darth
16:53
Maul, the initial 2 out of 10 output, we
16:57
got it to a 5 out of 10. And then by the
16:59
time I shipped it, it looked like this.
17:01
So, you'll see the biggest difference
17:02
here between the five and the shipped
17:04
version is Maul looks really bad here.
17:07
He's missing part of his arms. He's
17:09
constantly swinging through himself
17:11
where when we get to the shipped
17:12
version, his model looks way better. His
17:14
animations are way nicer. Same thing
17:16
here with Hogwarts. The world looks
17:18
super bare and empty. Starts to fill out
17:21
a little bit. By the time we ship, it
17:23
looks dramatically different.
17:26
And you can check all this stuff out in
17:28
the link below where I have this exact
17:30
thing linked. Just some different charts
17:32
about how these scores typically did
17:34
climb. And there are six different types
17:37
of revision notes that I typically send.
17:40
Those are the polish pass, the specific
17:44
issue pass, the lock and focus pass, the
17:48
praise and then set the gap pass, quick
17:51
fix pass, and then prefilming sweep. I
17:54
do this before I film the videos that
17:57
you see here on the channel. All right,
17:59
I get really excited for this part
18:01
because this is where we get to see our
18:03
work compound. And I didn't do this for
Step 6: Turn wins into skills
18:06
way too long and I'm kicking myself I
18:08
didn't start sooner. But basically, if I
18:10
have part of a build that is really
18:13
stand out that I believe I can take into
18:15
future builds, I will always turn it
18:17
into a skill. For example, I had a
18:21
really hard time forever to get
18:23
anthropic models to create decent
18:26
looking character models. Astra does it
18:29
very nicely, but it took me a while to
18:32
stop getting outputs that look like this
18:34
and start getting outputs that look like
18:36
this. To go from this complete lack of
18:38
detail to this high level of detail, I
18:41
don't want to have to reddo all of that
18:45
work every time I start a new build. So,
18:47
I have a character model skill that I
18:50
can pull in every single time. So, I've
18:52
used this for Darth Maul. I've used it
18:54
for Opus Ring. I've used it for Night's
18:56
Watch and a whole bunch of others. The
18:58
three main skills that you've seen in
19:00
some of my recent videos are my Voxil
19:02
world skill. We did this for Port Solace
19:05
and Rowanir. So, basically, I can pull
19:08
this skill and say, "Make me a Voxil
19:10
city in ancient Egypt." And it will
19:12
always make sure that it uses the same
19:15
engine and the same quality bar and will
19:19
have the same level of detail. So
19:21
basically, I can now build these
19:22
incredible voxal worlds in a single
19:25
prompt instead of hours and hours of
19:28
revisions. You see my dark crawler kit.
19:31
So this started off with Grimhold. It's
19:33
this really detailed 3D firstperson RPG
19:38
system. I took that same thing into
19:40
Night's Watch. I also took it into Opus
19:43
Ring. Same thing with the game character
19:46
kit that we just discussed. In fact,
19:48
pretty much all of these builds overlap
19:51
in multiple ways across multiple skills.
19:53
So, when we start stacking these skills,
19:56
it allows me to build games faster and
19:59
more efficiently because I'm now taking
20:02
previous work and I'm stacking it on top
20:05
of current things. And now, since I've
20:07
been doing this so long, I can stack
20:09
skill on top of skill on top of skill.
20:11
And I can create these games really
20:13
efficiently and much faster than
20:16
starting from scratch every single time.
20:18
And quick shameless plug, I have now
20:20
added all of my skills into my creator
20:23
bundle so you can just grab my skills
20:26
and pull them into your next build if
20:28
you don't want to start from scratch. In
20:30
my opinion, the $9 is worth saving the
20:33
hours. Nate, all right, if you've made
20:36
it this far, clearly you're serious
20:38
about building this stuff. And I want to
20:40
encourage you, if you're not already,
Step 7: Ship it
20:42
share what you're building with the
20:43
world. Just a few months ago, I started
20:45
posting the fun stuff I was making with
20:47
a AI on Instagram, and look what it's
20:50
turned into in a short amount of time.
20:52
I'd encourage you to do the same thing.
20:54
So, here's a few things that I do in
20:56
order to showcase my builds. First, I
20:58
create a showcase mode. I make sure
21:00
every chapter is selectable from the
21:02
menu, every track is unlocked, unlock
21:04
all the fast travel points. Basically, I
21:06
make this as easy as possible for both
21:07
myself filming the content, but also for
21:10
a player to be able to explore and
21:12
experience as much of the game without
21:14
having to spend too much time. Next, I
21:17
run a full pass for playability.
21:19
Basically, I have an agent go through
21:21
and play the entire game as a player,
21:23
make sure nothing is broken, though I'm
21:25
sure there are still plenty of bugs that
21:27
make it into production. I ask the AI to
21:30
capture a trailer from the file itself.
21:32
So, I say, "Hey, build me a 30-se
21:34
secondond trailer." And those are the
21:35
trailers you see in my arcade. Uh, one
21:37
quick note, I tell it never open on a
21:39
black screen. Right now, AI loves to do
21:41
this thing where the first one to 1.5
21:44
seconds are a black screen. That's the
21:46
worst way to lose a viewer. I give it a
21:48
page in my arcade. I put it in my arcade
21:51
and I get it out there for you to play.
21:53
All right, I'm not even going to pretend
21:54
like I'm a technical guy with all this
21:56
stuff. I'm much more of a creative. I
21:58
come from a marketing background, not a
The technical scaffolding
22:00
developer background. But here's the
22:02
scaffolding that's being used. And you
22:04
don't have to understand this part to
22:06
use it. There's some copy paste prompts
22:08
that you can come in here to build out
22:10
this scaffolding that I use to get
22:13
everything ready for production. There's
22:15
also some different tests here that I
22:17
ask for and some other items here that
22:20
might be helpful in your build process.
22:22
Okay, a couple quick bonus things. You
22:24
can check out the link to read the
22:26
different mistakes that I have made and
Bonus: mistakes, prompt builder and FAQ
22:28
have paid for in more ways than one. uh
22:31
and what I did to fix these mistakes.
22:34
Also, there's an area here where you can
22:36
build your own prompts, so you can fill
22:38
in some of these blanks and you can
22:39
start to at least get a starting point
22:41
for your prompts. And there's the same
22:43
thing for your revision notes. A couple
22:45
different free templates for you as
22:47
well. Some FAQs down here uh that you
22:50
might find helpful. And again, you can
22:53
get all of my skills, my builds, my
22:57
files, my games, and that's updated
23:00
constantly for just 9 bucks in my
23:03
creator bundle. But if you don't want to
23:05
do that, honestly, this here should be a
23:08
good enough place for you to start. If
23:10
you're still watching, thanks for
23:12
sticking with me. I know this was a
23:13
longer video. I really wanted to be
23:15
diligent in giving you as much
Outro
23:17
information as possible based on how
23:20
many people have asked for this video.
23:22
If I left anything out, if anything
23:24
doesn't make sense, just let me know in
23:26
the comments below and I will do my best
23:28
to get you an answer. Also, jump into
23:31
our Discord community, also linked in
23:33
the description. That's where I hang out
23:35
all day. That's the best place to get
23:37
your questions answered, best place to
23:39
showcase your builds, get feedback on
23:41
your builds, and we have some awesome
23:43
members in there who are dropping so
23:45
much value, sharing workflows, and
23:48
helping each other create better stuff.
23:52
And finally, don't just sit on this
23:55
information. Go ahead and use it to
23:57
build awesome games, awesome worlds,
24:00
make your imagination come to life, and
24:02
jump in that community and show me what
24:04
you've built.
