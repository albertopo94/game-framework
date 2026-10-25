I Built a Game in One Weekend
0:00
Can you actually build
0:01
your own playable game
0:03
in a single weekend?
0:04
How about a 3D,
0:06
regular like shooter with
0:08
the world nobody else
0:09
has?
0:10
Built from entirely AI
0:12
-generated assets.
0:14
I made it in
0:15
just two days, one
0:16
person only.
0:17
And I'm going to
0:17
show you the whole
0:19
workflow I used
0:20
from the very first
0:21
concept to playable game.
0:23
We're going to generate
0:24
environment assets, build up
0:26
the world,
0:27
generate characters, rig them
0:29
and add them all
0:30
to the game and
0:31
make them run.
0:32
And I'm going to
0:32
honestly break down where
0:34
AI succeed or where
0:35
you have to touch
0:36
it up manually
0:37
and how to move
0:38
fast. What I can
0:39
promise for sure, this
0:41
is going to be
0:41
fun.
0:42
Only one thing before
0:43
we start, I want
0:44
to answer why do
0:45
I make this video?
0:46
I do not want
0:47
to say that game
0:48
development is dead and
0:49
I do not want
0:50
to discourage those
0:51
in this industry, building
0:53
great games still require
0:54
time.
0:55
But I want to
0:56
encourage those who always
0:57
had a dream to
0:58
create a game or
1:00
do the first step
1:01
now it's possible and
1:02
you can get really
1:03
fast.
1:04
I've been in such
1:05
position myself and that's
1:06
what gives me motivation
1:07
to make such video.
1:09
So hit that like
1:10
button and let's get
1:11
started.
1:11
Okey dokey, so we
From Idea to Visual Concept
1:12
of course start with
1:14
the concept.
1:14
And the concept actually
1:16
is something insane.
1:17
I was actually thinking
1:18
about it like for
1:18
quite a while, we're
1:19
going to create
1:20
Req Comber Fighting Rats
1:22
as a treaty -regul
1:24
like shooter.
1:25
How about that? Well
1:26
that seems like someone
1:27
actually have to build
1:29
that game.
1:29
So why are we
1:30
going to show you
1:31
how I'm going to
1:31
address that?
1:32
So first of all
1:33
of course, we're going
1:34
to need to figure
1:34
out the concept.
1:35
So here are some
1:36
images that I generated
1:37
with Chat GPT2 this
1:40
time.
1:41
I started to like
1:42
this image generation model
1:43
even more than Nanobanana
1:45
Pro in a way
1:47
that it
1:47
gives more details. For
1:48
stylus stuff, I still
1:50
prefer Nanobanana Pro.
1:51
Okey so here's the
1:52
concept right, we do
1:53
have this quite recognizable
1:55
street and houses from
1:57
Rick and Morty and
1:58
we do have the
1:59
Rick cucumber himself and
2:01
the rats.
2:02
Bloody rats from Severage.
2:04
Anyway, then I was
2:05
thinking about the map
2:07
and here's what I
2:08
was thinking.
2:09
There will be houses
2:10
on the perimeter and
2:12
there will be a
2:13
park in the center.
2:15
So yeah, this one
2:17
is actually like too
2:18
big. I definitely don't
2:19
want it like that
2:20
big.
2:20
We're going to go
2:21
with the smaller size.
2:22
But it actually makes
2:23
sense because we can
2:24
go through it.
2:25
Right? And the actual
2:27
positioning will definitely be
2:28
a little bit different
2:28
and I was playing
2:29
around
2:29
like how to do
2:31
the park. So pretty
2:32
much I like the
2:33
idea here but I'm
2:35
going to extract some
2:36
ports and build up
2:37
them in a little
2:37
bit different way in
2:38
a way when I'm
2:39
going to position them.
2:39
In right after we
2:41
have to extract ports
2:43
and create them. If
2:44
you watch my child
2:45
you know how
2:46
important is that. Definitely
2:47
not making sense to
2:48
try to build up
2:49
anything like by one
2:50
pieces like
2:51
that will be a
2:52
difficult to process, not
2:53
much flexibility. I'm going
2:55
to create like small
2:56
parts
2:56
and combine them like
2:58
like fence for example.
2:59
So I'm flexible to
3:00
move fence around right.
3:01
So goes for any
3:02
other objects. I'm going
3:04
to have a few
3:04
houses, some other objects
3:07
from the street
3:08
and of course the
3:09
characters here is the
3:10
final version of the
3:11
rick cucumber and the
3:13
rats.
3:13
Characters by the way
3:14
I created with nano
3:15
banana pro because I
3:17
said like with less
3:18
details and stuff
3:19
like sort of like
3:20
easier. I don't know
3:20
why. Now let's create
3:22
models. This time again
3:24
I'm going to use
3:25
triple. I'm going to
3:26
drop images. I'm going
3:27
to choose multi view
3:28
and I'm going to
3:29
use smart mesh
3:30
from triple. Still in
3:32
my opinion this is
Creating AI Characters
3:33
the best generator yet
3:35
for 3D especially the
3:38
smart
3:38
mesh because we're going
3:39
to choose the reasonable
3:40
amount of polygons. Since
3:42
it's a full character
3:43
we're going to go
3:44
max. That should be
3:45
working and the generation
3:47
here is very very
3:48
fast and here
3:49
we already have the
3:50
model and the mesh
3:52
is extremely logical. I
3:54
don't know I just
3:54
like it. It's fast,
3:56
it's usable and all
3:58
things together just adds
3:59
up and make it
4:00
like just the best
4:01
choice for me and
4:02
my team.
4:02
The only thing if
4:03
you use smart mesh
4:04
you don't get it
4:05
textured right away so
4:06
you're going to go
4:07
to
4:07
texture tab and texture
4:09
later. That makes sense
4:10
because smart mesh allow
4:12
you to iterate a
4:13
few
4:13
times and like basically
4:14
you can get like
4:15
smart mesh in 5
4:16
to 10 seconds you
4:17
check around. It can
4:18
fail
4:19
so there's a free
4:20
retry because like it
4:21
takes an image but
4:23
if you use multi
4:24
view especially the
4:25
back view or like
4:25
side view you will
4:26
less likely have anything
4:28
in the problem on
4:29
the back. I got
4:30
some
4:30
issues like with long
4:31
tails but yeah that
4:33
can regenerate quickly and
4:35
here we go and
4:36
this result is
4:37
pretty much amazing. You
4:38
see what you see
4:39
I don't even think
4:41
I'm gonna edit anything
4:42
we're gonna
4:42
export that and continue
4:44
with the rats. Absolutely
4:45
the same process with
4:47
the rats so we're
4:48
gonna also go
4:48
with 20k polygons because
4:51
this character right. Let's
4:53
do generation here we
4:55
have the mesh. Pretty
4:56
amazing as you ask
4:58
pretty pretty good. Okay
4:59
all this cars have
5:01
some additional density. I
5:02
think that's
5:03
fine. Potentially can generate
5:05
like in less so
5:06
now let's go to
5:07
texture tab with all
5:08
the same
5:09
textures. Let's do the
5:11
texture and this is
5:12
just an amazing result
5:13
right and again like
5:14
that's
5:15
low poly and the
5:16
mesh is logical you
5:19
know all these loops
5:19
yeah maybe they are
5:20
not 100 % perfect
5:21
for
5:22
animation but for my
5:23
roguelike experience especially with
5:25
the camera on top
5:26
that's more than enough.
5:28
Yeah here we go
5:28
the perfect one let's
5:29
grab it and next
5:30
step I'm gonna first
5:31
address characters
5:32
and starting to compile
5:34
them in Unreal Engine.
Rigging & Animation Setup
5:36
Okay so here we
5:36
have our rick cucumber
5:38
so I'm gonna
5:39
draw a quick cucumber
5:39
to blend there and
5:41
reset the rotation here
5:43
right away because like
5:44
triple has
5:45
like this 90 degree
5:46
rotation then I'm gonna
5:47
export in fvx and
5:48
we're gonna go to
5:49
accurate rig.
5:50
That's again free software
5:52
where we can rig
5:52
animations are paid but
5:54
we don't really need
5:55
them because
5:56
we're gonna export by
5:57
Unreal Engine skeleton and
5:59
retarget in Unreal Engine.
6:01
So the process here
6:01
look quite simple again
6:03
you set the markers
6:04
for the body then
6:05
you set the markers
6:06
for the hand it
6:07
supports like four fingers
6:08
I think three fingers
6:10
and five fingers in
6:11
my case it was
6:12
four fingers so
6:13
we're gonna set the
6:13
markers let's go then
6:15
check out some poses
6:16
and yeah you already
6:17
see it looks quite
6:18
quite good and yeah
6:20
then the reason why
6:21
I like it is
6:22
that you can export
6:23
a target for Unreal
6:24
Engine 5.
6:25
Let's do that now
6:26
we're gonna bring it
6:26
back to blender and
6:28
there might be a
6:29
need in my case
6:30
it was
6:30
two fixed -up bits
6:32
assets so they do
6:33
not affect the body
6:35
in a natural way
6:36
so like a cucumber
6:37
body
6:38
should stay in rigid
6:39
whenever we move hands
6:41
so you can see
6:41
the shoulder here is
6:42
sort of affecting
6:43
some areas so I
6:44
had to actually go
6:45
around and paint well
6:47
basically painting with blue
6:49
is painting
6:49
a setting like the
6:50
which to zero meaning
6:51
that the shoulder will
6:53
not affect any area
6:55
of the body which
6:56
is like cucumber body
6:57
so that was pretty
6:58
much the only thing
6:59
I had to do
7:00
a little bit on
7:01
the shoulder
7:02
themselves etc so here
7:04
we go wait painting
7:05
can look scary but
7:07
it's actually very very
7:09
easy right
7:09
like it's basically you
7:10
set like which bone
7:11
affect what part of
7:13
the object and we're
7:15
gonna actually
7:15
drop it to Unreal
7:18
Engine right away so
7:19
here moment of full
7:20
disclosure I decided to
7:22
get started with
7:23
the team plate of
First Playable Build
7:24
a rug you like
7:25
and iterate on top
7:26
of that so here's
7:28
the team play that
7:28
I was using
7:29
it cost $50 in
7:31
my case it's like
7:32
in type -out for
7:33
me it looks like
7:33
a fair deal it
7:34
has all the basics
7:36
it's not perfect it
7:37
doesn't have like all
7:38
the stuff but again
7:39
later with cloth cloth
7:41
we can iterate
7:42
on that and that's
7:43
super easy at least
7:44
all the basics are
7:46
here and we can
7:46
start testing okay so
7:48
I
7:48
gonna upload my guy
7:50
here and set the
7:51
materials retarget animations and
7:54
attach the weapon so
7:56
in just
7:56
15 minutes I replace
7:58
it the character boom
7:59
and we already can
8:00
test it out let's
8:01
do the same thing
8:02
absolutely identical process I
8:04
gonna do with the
8:05
rat but for the
8:06
rat it was a
8:07
bit easier since I
8:09
didn't needed to change
8:11
any weights like this
8:12
pretty standard body right
8:14
close to human yeah
8:16
the
8:16
head is not but
8:17
I'm not animating mouse
8:18
and head and accurate
8:19
actually handled it very
8:21
nicely so here
8:22
you can see the
8:22
whole process for fingers
8:24
booboo and testing animations
8:26
there look very very
8:27
nice yeah I
8:28
mean pretty pretty fantastic
8:30
job so we don't
8:31
really need to go
8:32
any further and I
8:34
just gonna expert that
8:35
in right away bring
8:36
it to the Unreal
8:37
Engine and set the
8:38
materials also gonna need
8:40
to send handler for
8:41
the weapon just locate
8:43
it nicely and we
8:45
can actually replace it
8:46
for the zombies right
8:48
so basically
8:48
the team played as
8:49
a bus shooting zombie
8:50
okay and here's the
8:51
very first test in
8:52
the demo playground of
8:54
course with just the
8:54
places stuff and now
8:56
we're gonna think about
8:57
building location but if
8:59
you guys
8:59
series about making your
9:00
own game I have
9:01
extremely good news for
9:02
you since I launched
9:03
my pool 3D AI
9:05
course about how to
9:06
make 3D character from
9:08
scratch with AI in
9:10
just one week I
9:11
gonna give you 10
9:12
%
9:12
of 3D skills knowledge
9:14
about all best 3D
9:15
AI tools how to
9:16
plug them in the
9:17
real efficient workflow
9:19
so you can achieve
9:20
90 % of any
9:22
of your ideas we
9:23
already got amazing feedback
9:25
our students creating
9:26
characters and more and
9:28
enjoy the process but
9:29
I understand not everyone
9:30
can afford that so
9:31
for those
9:32
in need or difficult
9:33
circumstances I want you
9:35
to let me know
9:36
in the comments about
9:37
your story
9:38
what do you want
9:38
to create how this
9:40
course will make your
9:41
life better I gonna
9:42
read it carefully
9:43
and for three of
9:44
you I gonna give
9:44
it out for free
9:45
okay back to world
9:47
assets so here are
9:48
the objects
Generating a Complete Asset Pack
9:49
we're gonna create and
9:50
here we're gonna use
9:51
triple as well but
9:53
for this environment assets
9:55
we're gonna
9:55
move a little bit
9:56
smarter and in smart
9:57
mesh we're gonna need
9:58
to choose exact amount
10:00
of polygons so for
10:01
some smaller assets we
10:02
can go with like
10:03
three to four five
10:04
thousand polygons for bigger
10:06
assets we
10:06
can go like ten
10:07
twelve thousand polygons so
10:09
evaluate yourself carefully how
10:12
it's really needed so
10:13
you
10:13
don't need two dense
10:14
polygons and it also
10:16
will affect the optimization
10:17
and that's basically just
10:19
not needed make sure
10:20
that the shape transfer
10:21
it nicely no hard
10:23
triangles on shading and
10:25
that's it
10:26
so here are all
10:27
objects that I created
10:28
you can see fence
10:29
for example is only
10:30
two thousand
10:31
polygons and that's pretty
10:33
enough that there is
10:34
no need in more
10:35
for car can be
10:37
a little bit bigger
10:37
just to keep the
10:39
shape and here you
10:40
can see all objects
10:41
in blender final preparation
10:43
usually you might
10:45
want to adjust some
10:47
pBR maps here maybe
10:48
do some baking additional
10:50
polishing in my case
10:51
I don't really
10:52
need all of that
10:53
I can just align
10:54
the scale rotation pivots
10:56
and blender decal origins
10:57
for easier
10:58
later use in Unreal
11:00
Engine and of course
11:01
guys you always ask
11:03
to show you the
11:04
wireframe I'm gonna show
11:05
your wireframe on all
11:07
objects actually for some
11:08
objects I could definitely
11:10
go lower but overall
11:11
I'm
11:11
quite satisfied some objects
11:13
yeah you can see
11:14
are a bit denser
11:16
that it can be
11:17
but yeah I just
11:18
wanted to
11:18
move faster and keep
11:19
all details nicely overall
11:21
I think they're pretty
11:22
much optimized great so
11:24
all
11:25
these assets that you
11:26
see was generated with
11:27
triple without any edits
11:29
from my site and
11:31
if you want to
11:32
try it out guys
11:32
still this is my
11:34
honest recommendation I know
11:35
I recommended like quite
11:37
a few of my
11:37
videos
11:38
but what can I
11:39
do if it's still
11:40
top one by all
11:42
means right it's good
11:44
and low poly is
11:45
good
11:45
and segmentation they recently
11:47
updated like segmentation to
11:48
V2 it's actually way
11:51
better than it
11:51
was before before I
11:53
think Hunian was taking
11:54
the lead so it's
11:55
really a best 3d
11:57
generator not only by
11:58
my
11:58
opinion like the daily
12:00
there's like thousands of
12:01
what daily only on
12:02
the arena and triple
12:03
basically
12:04
you can generate images
12:05
is also very good
12:07
HD model so smart
12:08
meshes are more about
12:09
low poly there's
12:10
very nice HD model
12:12
and you can also
12:12
do the Ritzipology you
12:14
can upload your own
12:15
models professional
12:16
workload might be to
12:17
get the model fine
12:19
tune it drop it
12:20
back here texture Ritzipology
12:22
quite a lot of
12:22
use cases and it
12:23
really works now when
12:25
we have all objects
12:26
done there's one missing
12:28
part we're
12:28
gonna need it's style
12:29
it pilot textures and
12:31
I have a great
12:32
news for you I
12:33
was actually waiting to
AI Materials & Textures
12:35
test it out and
12:36
now I'm gonna show
12:36
you guys a practical
12:38
use of patina from
12:39
full .ai they released
12:41
it like around two
12:42
three weeks ago and
12:43
what it can do
12:44
is very very cheap
12:45
generation of PBR
12:46
set of maps from
12:47
image or text right
12:49
so here we go
12:50
here's the example right
12:51
it can generate all
12:53
set in why do
12:54
we need it kiss
12:54
we have some surfaces
12:56
such as concrete such
12:57
as road such as
12:59
grass
13:00
sand etc which we're
13:02
gonna need for brushes
13:03
so we can paint
13:04
the area in landscape
13:06
mode and
13:07
unreal engine so look
13:09
at this beautiful style
13:10
of grass I just
13:11
generated for just eight
13:12
cents
13:12
I'm using it on
13:14
full it's not by
13:14
subscription is by use
13:16
so you can fulfill
13:17
your balance by like
13:18
few dollars and be
13:19
able to use it
13:20
and here we go
13:21
so looks just amazing
13:22
I tested it in
13:23
blender so you
13:30
and we can also
13:31
connect all the rest
13:32
of the maps and
13:33
look how beautiful it
13:35
is oh that's really
13:37
really cool look at
13:38
this stones right so
13:39
there is a normal
13:40
map like it really
13:41
really works and with
13:42
all that ready we
13:43
are ready to move
13:44
to unreal engine and
13:46
build up the location
13:47
that is the most
13:48
fun part
13:49
we have all the
13:50
building blocks and we
13:51
can just go and
13:53
build it up so
13:54
I unfortunately did not
13:55
record it
13:55
like how I built
13:56
this center road that
Building the World
13:58
just a square road
13:59
that goes around and
14:00
a little bit of
14:01
walls
14:01
but the rest of
14:02
the process pretty much
14:03
recorded so we're just
14:04
going to locate all
14:06
the assets
14:07
like that and build
14:08
up the houses and
14:09
you can see that
14:10
things started to look
14:11
nice right away
14:13
and you can see
14:13
that things look good
14:15
together because we're generating
14:16
basically them in one
14:17
style
14:18
they're fit you don't
14:19
need to go and
14:20
spend hours to find
14:21
assets from different assets
14:23
back to
14:24
combine them no they're
14:25
all in same style
14:26
they're fit and that's
14:28
why the things look
14:29
good together when
14:30
we do a composing
14:31
one thing that I
14:33
actually did bought on
14:35
the fact was styled
14:37
forest asset pack
14:38
for grass and foliage
14:40
basically which includes trees
14:42
grass and some small
14:43
objects that you can
14:44
usually see in forest
14:45
but mainly because of
14:47
grass and trees because
14:48
they're nicely animated and
14:50
stuffed and well technically
14:51
you can do that
14:52
with AI as well
14:53
but you're gonna need
14:55
to split it
14:55
in more parts do
14:57
the rigging and etc.
14:58
and the same thing
14:59
I also used for
15:00
styled water I already
15:01
had
15:02
this boat and I
15:03
just needed it like
15:04
for some small area
15:05
in the park to
15:06
add this styled water
15:07
effect
15:08
under this center building
15:09
you're gonna see later
15:11
the budget damage is
15:12
not that big the
15:13
styled forest
15:14
cost only 20 dollars
15:16
I think that's very
15:17
fair price water costs
15:19
50 bucks but I
15:20
already had it
15:21
before those are not
15:22
really static assets but
15:23
more like a dynamic
15:25
assets and the good
15:26
thing that
15:26
they are already optimized
15:27
I believe at some
15:28
point we will be
15:29
able to generate that
15:30
but in different
15:31
way not as a
15:32
treaty but more like
15:33
a procedural treaty and
15:34
I already do some
15:35
experiments with fabled
15:36
5 but the funny
15:38
thing did they I
15:38
record the video I
15:40
just woke up and
15:41
I see this news
15:42
that now I do
15:43
not have access to
15:44
fabled 5 I'm gonna
15:46
go back to 4
15:47
.8 opus I don't
15:49
know for how long
15:50
it will be but
15:51
I'm not US residential
15:52
I live in Thailand
15:53
for a while already
15:55
well that's not gonna
15:56
stop us let's
15:57
actually move on so
15:58
yeah this animated trees
16:00
and bushes really adds
16:02
up to the image
16:03
and just like
16:04
that I gonna go
16:05
and continue building up
16:06
the street and look
16:07
how nice it looked
16:08
also noted I have
16:10
a
16:10
brush that's pinned to
16:11
it that sand styled
16:13
sand texture so I
16:14
do the borders right
16:16
so to give it
16:17
like a nice nice
16:18
look I think it
16:19
looked just amazing right
16:21
away similar way exactly
16:22
I built all the
16:24
rest of the houses
16:24
and now it's time
16:26
for the park so
16:27
this is the part
16:27
that I didn't show
16:28
you
16:28
to our builds but
16:29
again that was pretty
16:30
easy again here's the
16:31
material that I used
16:32
for the
16:33
a rocky road now
16:34
we're gonna dig round
16:36
a bit for our
16:37
water later so here's
16:39
the building that we're
16:40
gonna place in the
16:41
middle then we're gonna
16:42
need the sand texture
16:43
and I'm gonna add
16:45
the plane with
16:45
that water that I
16:47
have right so I'm
16:48
gonna set the size
16:49
boom here is this
16:50
look just fantastic I'm
16:52
gonna add up four
16:53
bridges so we can
16:54
go around here a
16:55
little bit rocks actually
16:56
rocks I generated
16:57
the trip as well
16:58
and a little bit
16:59
of fine tune how
17:00
cool is that just
17:01
amazing and we need
17:03
to add a
17:03
little bit to the
17:04
park itself okay so
17:06
I'm gonna use these
17:07
same exact tools at
17:08
same exact
17:09
toilet texture for sands
17:11
and grass and the
17:13
dynamic grass as well
17:14
right boom boom boom
17:15
flowers a little
17:16
bit there they're adding
17:18
trees and we already
17:19
have an amazing beautiful
17:21
location in Central Park
17:23
well
17:23
trees making a lot
17:24
and guys I just
17:26
want you to take
17:27
a look on what
17:28
I built in less
17:29
than two days
17:30
actually it was way
17:31
faster than two days
17:33
let's say I even
17:34
had a break to
17:35
go outside and yeah
17:37
this
17:37
look just amazing the
17:39
whole location I mean
17:40
you can obviously iterate
17:41
more and add more
17:43
and more
17:43
details but for me
17:44
it was very very
Final Environment Reveal
17:45
fun to play with
17:47
I'm still amazed like
17:48
a kid that I
17:50
can iterate
17:50
so fast and do
17:51
so much right again
17:52
like in just two
17:53
days get so far
17:55
build up the location
17:56
then I can
17:57
focus on some logic
17:58
stuff but it already
17:59
look good like it
18:00
give you extra motivation
18:01
so with all this
18:03
location done how about
18:04
we actually start playing
18:06
so are we ready
18:07
to start playing so
18:09
of course I
18:10
couldn't help myself to
18:11
not make this funny
18:12
dancing animation anyway let's
18:15
try it out so
18:16
the
18:16
team played a working
18:18
pretty nice it's not
18:19
perfect I mean at
18:20
least the post effects
18:21
they need some
18:22
upgrade and that is
18:23
basically what you can
18:24
do with a setup
18:25
of cloth if you
18:27
haven't seen my last
18:28
video
18:28
about clothes plus Unreal
18:30
Engine definitely take a
18:31
look and you will
Playing the Game
18:32
know that moving from
18:33
here
18:34
iterate on the game
18:36
mechanics adjusting something it's
18:38
really possible with clothes
18:40
it even will do
18:41
the blueprint stuff etc
18:43
and that's just amazing
18:45
how far we can
18:45
go in this video
18:46
I wanted to focus
18:47
more
18:47
on treaty components and
18:49
show how fast you
18:50
can iterate can't wait
18:51
to read your comments
18:52
guys what
18:52
you think about it
18:53
this is of course
18:54
not the hundred percent
18:56
ready game it's more
18:57
like a playable
18:58
prototype but as a
18:59
starting point it's super
19:01
exciting and they can
19:02
definitely give you extra
19:03
motivation to move on
19:04
iterate when we can
19:05
build something fast touch
19:07
it fill it and
19:08
enjoy that was
19:09
step like and subscribe
19:10
and see you in
19:11
the next videos
