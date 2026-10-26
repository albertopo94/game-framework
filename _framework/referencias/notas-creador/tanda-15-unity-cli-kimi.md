Unity CLI + Kimi K3: A New Era of AI Game Development
0:00
Unity releases CLI and honestly that's a
0:03
banger in my opinion it outplays Unreal
0:06
Engine significantly and it's a huge
0:09
move for a genetic game dev. Moreover,
0:12
we have crazy good opensource scheme K3
0:15
which just recently released weights on
0:18
hugging face. You can go take a look
0:21
right now. And in the comments guys, you
0:23
are suggesting why don't we plug these
0:26
guys together? Kim K tree and new Unity
0:29
CLI. That will be amazing. I have a
0:31
bunch of crazy tests for today. We're
0:33
going to do Unity CLI different game
0:36
challenges. We also going to talk about
0:38
Unreal Engine and why it's not working
0:40
that great. Do not skip that part. It's
0:43
very important. So, you know what to do.
0:45
Hit that like button. Subscribe if
0:47
you're still not. And let's get started.
0:49
All right. First of all, Unity CLA. What
0:51
is it about? It's just amazing. Well,
Installing Unity CLI & Connecting Kimi K3
0:53
basically that's the new way of
0:55
interaction with Unity all by code and
0:58
in runtime. I mean, it significantly
1:01
reduce the time for creating a script,
1:03
running the script, getting the
1:04
feedback, etc. like it was with old MCP.
1:07
Now, it basically gives full access and
1:09
freedom to run scripts along the way and
1:12
even in runtime. So, how do we install
1:14
it? Let me explain briefly. First of
1:16
all, we're going to need Kimmy since I'm
1:18
going to test with Kimmy. So I going to
1:20
install both Kimmy CLI and also desktop.
1:24
It's quite simple. Just go on Kimmy
1:26
website and you're going to get like the
1:28
CLI. You basically open PowerShell in my
1:30
case and just install it in one command.
1:33
Then there is like Kimmy login and then
1:35
you just login it to your account.
1:37
That's pretty much it. You can also run
1:39
it through Kimmy web command that will
1:41
open this interface right in browser. So
1:44
that's like there are plenty way how you
1:46
can run it. You can also do the desktop
1:48
app if you prefer. For me, I usually use
1:50
CLI, but to show you the chat history
1:53
and all that stuff, I'm going to use
1:54
Kimmy web. The next step is to install
1:57
Unity CLI. And here, if we would take a
1:59
look on the installation, there will be
2:01
just a simple oneline command. We're
2:03
going to need to open terminal or
2:05
PowerShell. Just go there and paste that
2:08
command and Unity CLI will be installed
2:10
right away. All right. When it's
2:12
installed, close the window, open the
2:15
PowerShell again and run the command
2:17
unity authors
2:20
and suggest to you to login in your
2:23
account. I will going to do that with
2:24
Google. After that, you're going to see
2:26
this message that you're now signed in.
2:29
That's exactly what we need. Now, now
2:30
CLI is installed. But to install the MCP
2:33
and pipelines to connect it inside your
2:37
project. So, here's how it done. So, in
2:38
official instruction, there's two way.
2:40
You either go into the project and
2:42
install the true packages or you can run
2:44
a true terminal like Unity pipeline
2:47
installed. So I don't have project yet
2:49
created. So I'm going to go create new
2:51
project in version 6000. Of course, of
2:54
course this only in this version it
2:56
supports. So we're going to create a new
2:57
project. Go to general. Going to go to
3:00
package manager and we're going to find
3:02
it by com.unity.pipeline
3:04
and press install. Well, basically this
3:07
actually installs the MCP and this evol
3:10
support. So when this package is
3:12
installed in the project, we have access
3:14
Unity CLI have access and your agent
3:16
will have access to this project. Now to
3:19
test if it works, we can open PowerShell
3:21
and run the command Unity editors
3:23
running and it will actually show us
3:25
what editors it can see and we can see
3:28
that this Kim test project that I just
3:30
created is visible for Unity CLI which
3:33
is exactly what we want. Now the very
Setting Up the MCP Pipeline for Unity
3:35
last step is to configure MCP for our
3:38
agent. And if you have anything but
3:39
Kimmy, you can actually install it very
3:41
easily like Unity MCP configure CL for
3:44
example, which will install it to my
3:46
cloud desktop. But we're going to need
3:48
something else. And I was thinking like
3:50
maybe they added for Kimmy. But no, if
3:53
you run the list command, there is no
3:54
Kimmy. So we're going to need to do that
3:56
manually. The good news is very simple.
3:58
You can either copy the MCP file from
4:03
your code [laughter] or we're going to
4:06
create it ourself. So here we go. I'm
4:08
going to use VS code or you can use
4:10
cursor. Just open that unity project
4:12
[music] in that visual code or you can
4:15
actually use text editor if you want.
4:17
Now here in the project let's create new
4:19
text file when we're going to paste this
4:21
code where command has passed to unity
4:24
and the third argument is exactly that
4:26
pass visible for unity CLI or pass to
4:30
your project basically that's pretty
4:32
much it you can copy it like this or I'm
4:34
going to put it all in the article link
4:36
will be in the description. Now the
4:37
important thing we're going to name this
4:39
file asmcp.json
4:41
and that's pretty much it. Now we're
4:44
going to need to create new chat in
4:45
Kimmy in that exact folder or just run
4:48
the CLI in that folder anyway will work.
4:52
Of course, we're going to set max
4:54
thinking in YOLO mode which is similar
4:57
to bypass permission in cloth. And let's
5:00
test the connection. And it seems that
5:02
yes, the connection is there. Very nice,
5:04
super easy. I face zero problems. Now,
5:07
let's do the first test. Okay, first
AI Builds Real 3D Games (10 Live Tests)
5:09
test. How about we create a 3D game? you
5:12
know this stack to but I actually asked
5:14
it to make it a little bit nicer than
5:16
just stacking stuff. some small
5:19
animation on overhang slices and yeah
5:22
basically you can see the prompt on the
5:24
screen as usual and yeah basically this
5:26
is explanation we have boom boom boom we
5:28
have stacks we need to press in the
5:30
right time let's check the results okay
5:32
so here we go and woo right away I can
5:36
tell that first of all I like the V
5:38
effects here I mean I like how the
5:40
slices fall down with this animation
5:42
maybe the animation of stacking is a
5:45
little bit boring but you see it works
5:47
the camera is a A little bit off to the
5:49
lead, but okay, let's go. Well, it seems
5:52
easy, but I mean, [laughter] it's not
5:53
easy. Look, I really enjoy this
5:55
animation. Like, oh, wow. All right.
5:58
Dang. I mean, that's actually cool.
6:01
Okay. Okay. Okay. Well, I'm playing more
6:04
bad with each attempt. Like, how come?
6:05
Anyway, that's quite not bad results and
6:08
that's playable and actually fun. So,
6:10
how much it takes? So, here we can see
6:12
quickly the process how it did that and
6:14
took quite a while. You can see a lot of
6:17
tool schools, etc. And I actually
6:19
decided to check how many tool schools
6:22
it does. And let's reveal the stats. I
6:25
did two prompts. First to build, second
6:27
to upgrade the visuals. Total they took
6:29
2 hours 17 minutes. This much tokens,
6:32
335 model calls, and it only cost around
6:36
10 bucks if you're going to use that.
6:39
And if we recalculate it by API cost, it
6:41
will be around N bucks. Of course, true
6:43
subscription that's more efficient, but
6:45
again, we need some numbers. Here you
6:47
go. And this is honestly insane. This
6:49
amount of calls to MCP and they're
6:52
really, really faster. I enjoyed it a
6:54
way more than running through MCP. And
6:56
my last video about making portal game
6:59
with Unity and MCP. I just finished that
7:02
video when the CLI was released. I was
7:04
like, ah, it's booming so fast. Now,
7:07
let's do one more test. And also, we're
7:09
going to talk about Unreal Engine soon.
7:10
The test is very simple. pingpong game,
7:12
right? Let's try to make it nice. Nice
7:14
animation. Again, this quite simple
7:17
game, but just try to make it working
7:19
and fun. There we go. Okay, nice. Well,
7:23
the effects are solid. I think there's
7:25
like a small bug still. There's like
7:28
some square that I can see when it hits
7:30
or touches, but overall, okay, this just
7:33
works, right? And that was actually
7:35
quite fast. Nice. Okay. Very simple
7:37
game, but you can see it works quite
7:40
nice. Okay. Okay. Boom. Nice. So, how
7:43
much time it took? Actually, it also
7:46
took two prompts. Again, all the time it
7:48
was building the game and then like I
7:50
did the visual pass. So, total time 1
7:53
and 1/2 hours, this much tokens and 8.5
7:57
bucks, 236 model costs, which I think is
8:01
actually fine. Now, I also did the same
8:03
test. I actually use VU and Unreal
8:06
Engine MCP. If you are into Unreal
8:07
Engine, take a look on my recent videos
8:09
about new MCP and all that stuff. I did
8:13
quite a lot of tests and I actually made
8:15
it. Here is the result in Unreal Engine.
8:19
Same game. Okay, it's a little bit
8:21
different animation. Again, this also
8:22
made by Kimmy. You can see it actually
8:24
works. I think it felt a little bit more
8:27
laggy when I played it, but still I made
8:30
it. but took me way more time and
8:32
revisions to do the same results I did
8:35
in two prompts with Unity CLI and that's
8:38
the same model and initially I was
8:39
thinking to do same test in Unity and
8:42
Unreal Engine but just after first test
8:44
I started to hate Unreal Engine and guys
8:47
this is so much better to work with code
8:50
first engines when it comes to aentic
8:53
approach I was also having so much fun
8:55
working with GDot take a look on one of
8:58
my recent video it's so smooth, you
9:00
know, like you just say something and it
9:02
does the job. You don't need to like do
9:04
plenty of screenshots and, you know, do
9:06
the guidance or like go and click all
9:08
the buttons like check this spaghetti of
9:11
blueprints, etc. So, sorry. We're going
9:13
to do only Unity in this video at least.
9:16
Next test, something fun that I wanted
9:18
to try long time ago. We're going to
9:20
create a spider walker with procedural
9:23
legs. How about that? There will be no
9:25
animation, but there will be plenty of
9:27
legs. And we're going to need to make
9:29
sure there actually goes follow the
9:32
surface, right? Prompt is on your screen
9:34
like you can see what's going on. Let's
9:36
try it out. Dang, look at this. Wow. It
9:40
is just great. The spider itself, I mean
9:43
like not perfect like Okay. But look,
9:46
look at this. Look at this. Okay. Okay.
9:48
Okay. Your legs are stretching a little
9:50
bit, but just look at that. Wow. Okay.
9:53
Nice. I know in Unreal Engine there's
9:55
like some setup that allow to do that
9:58
quickly, but again like I also tried it
10:01
and it requires a lot of time to set it
10:03
like for your custom character. So
10:05
basically you need to set the bones and
10:07
then like do this physics anyway and I
10:10
think it did great job here right well
10:13
can be improved like adding like physics
10:16
to the main body but I think that's a
10:18
really good job and the location is look
10:21
fine for playground. So how much time it
10:24
took? Three prompts almost 2 hours.
10:27
Well, it less in terms of model cost,
10:29
but additional prompts was mostly for
10:31
visual stuff. So you guys see better
10:33
image and it could cost me around 12
10:35
bucks if I use API. And I also prepared
10:38
some fair feedback so actually first
10:42
prompt it was a little bit ruined and
10:44
with second prompt it actually fixed all
10:46
that stuff. So I actually tested it and
10:48
addressed the feedback. But overall in
10:50
three prompts here's the result. Maximum
10:53
honesty test number two something that I
10:55
always like to stress test is shaders
10:58
prompt is on your screen like again like
11:00
five shaders like dissolve hologram lava
11:03
tune vapes. Let's take a look on the
11:04
results. All right, here we go. I think
11:06
I should be asking like to be able to
11:09
walk around. Okay, so let's take a look.
11:11
I also added like sixth one just to show
11:14
like simple lit again default state.
11:16
Okay, dissolve works, lava works,
11:19
hologram works, and I also did a test
11:21
like in Gdote also. Hologram somehow
11:24
like they know how to do that. I really
11:25
don't know what's going on with the tune
11:27
shader. I guess maybe like the sphere is
11:29
not the best example for toune shader
11:31
and the waves and waves actually also
11:33
working nice. Okay, not bad. Let's see
11:36
how much time it took. Well, actually
11:38
took quite a while. It took me three
11:40
prompts in almost 2 and 1/2 hours. And
11:43
yeah, that's quite a long time. I guess
11:45
I was not really specific. Anyway, next
11:47
test. This one is actually more fun.
11:49
Crossroad game. You know that game that
11:51
we played on button phones. The idea is
11:54
very simple. I want it in 3D like we go
11:58
through the road. There's bunch of stuff
11:59
happening. Prompt is on your screen.
12:01
Let's review the results. I of course
12:03
did a visual pass, guys. Not a secret.
12:05
But this one was already playable at the
12:08
first sign. And that's why I decided
12:10
like to improve it a little bit. And
12:12
this one actually works. Look. And there
12:13
is some sound design that I added. Okay.
12:17
And I also like the dynamic, you know,
12:19
like say it jumps the a little bit like
12:21
shaking of the screen. All the small
12:23
details, but I mean it makes sense. It
12:25
make it playable. Boom. Boom. Boom. And
12:27
there is even a bee or butterfly flying
12:30
around. Okay. And yes, it's indeed
12:32
infinite. So we can go go. Okay. Nice.
12:36
And what about time? Okay. So there was
12:39
four prompts to get it done. one to do a
12:42
core, two visual passes, and one bug fix
12:45
totaling 5 hours, 544 model calls, this
12:49
much tokens, and it could cost me like
12:51
23 bucks if I going to use it through
12:53
API. And it might seems long, which I
12:56
also think so, but Clo Opus 5 probably
12:59
going to do that like not much faster,
13:02
like maybe 3 hours. And I definitely
13:04
think Clo Opus 5 can do better job. But
13:07
there is a video where I compared Kimmy
13:10
and Clo Opus 5 and Opus 5 is just
13:14
insanely expensive [music] and this
13:16
model if you have a lot of VRAM or you
13:19
are making friends with co of Nvidia you
13:21
can run it locally and the results are
13:24
comparable for real fair feedback also
13:26
on the screen you can pause to take a
13:28
look if you want next one test number
13:30
six let's do a little bit music so how
13:32
about procedural music right so there
13:35
will be some synthes synthesized music
13:38
in runtime and also it should be
13:40
supported by some 3D visuals. Okay, how
13:43
about that? Right, I saw some cool
13:45
similar tests. Let's try it out. Okay,
13:48
so we basically have three modes. Okay,
13:51
it's very simple visual, but I think it
13:54
did the job that I asked it. Like music
13:57
even sounds meaningful. Well, it makes
13:59
sense like it's not just random noises.
14:02
So, okay. Okay. Cannot say like I'm
14:04
really impressed. I think that's simple
14:07
test because music is like mass in some
14:10
way or I don't know let me know what you
14:12
think about this test and test [music]
14:14
in general maybe you have great idea for
14:16
the next videos drop the comments I read
14:18
all of them so how much it cost and fair
14:21
feedback is on your screen let's move to
14:23
the next test okay test number seven and
Why Unreal Engine Struggles with AI Agents
14:26
I actually lied a little bit this one
14:28
will be in Unreal Engine and this is
14:30
also the reason why I decided not to do
14:33
more test in Unreal Engine so the idea
14:35
was like to do some stuff at Nagara and
14:38
yeah, we're basically demolition like
14:40
we're going to shoot with canon and try
14:42
to destroy some objects. Let's see what
14:44
it made. So, here is the first test and
14:48
yeah, we sort of like shoot it like
14:50
canon like goes really fast and this
14:53
nagara effects like I think look
14:55
terrible like you cannot even see the
14:57
cannon bullet because yeah, it covers
15:00
instantly with the nagara. So, okay.
15:01
Then I did like the wooden shed. And
15:04
we're also going to test it with the
15:06
brick wall. But yeah, this effects are
15:08
terrible. Also, just to show you how
15:10
destruction works. Here's with disable
15:12
it nagara. You can see like Yeah, I'm
15:14
shooting like and I mean the physics
15:16
like uh it's not bad, right? You can
15:19
press T for a slow mode. Yeah, I also
15:21
ask it for that. Yeah. So, it's not that
15:24
bad, right? But I was about to test
15:26
thing like this shaking of the screen.
15:29
Crazy. that I was about to test Nagara
15:31
and guys to be honest that's insane like
15:34
just for this test it took me seven
15:37
hours just think about that like right
15:39
and there's a problem with the way how
15:41
it review itself it tries to make a
15:43
screenshot like the pass is quite long
15:45
right so it's quite terrible and takes
15:47
long time and you don't really get that
15:49
fast again I think with Unreal Engine
15:52
you need to know all that stuff like to
15:55
guide it in the right way and I mean use
15:57
it like different way or like just do
15:59
code first projects like on C. I'm a bit
16:02
frustrated from this test again and as I
16:04
said like I decided not to do any more
16:06
test with Unreal Engine. Test number
16:07
eight, Suika merge. Well, this very
More Stress Tests: Physics, AI & Runtime Systems
16:10
popular genre like of advertisement
16:14
game, right? You know this annoying
16:16
game. Well, but concept is simple. We
16:17
are dropping some stuff and they're
16:19
merging into bigger bigger beer ship.
16:21
The prompt is on your screen. Let's take
16:23
a look at the results. The visuals are
16:25
well it's in 3D but again like I need
16:27
shading and stuff like it definitely be
16:29
better. I did not like a lot of visual
16:32
passes here but everything works. Yeah
16:34
well everything works I think like this
16:36
is like very simple thing but again
16:39
doing that in wrong stack can take you
16:41
so much nerves and that's like quite
16:43
frustrating. Well why it's not merging
16:45
right? Okay. Okay. So there is still
16:47
some problems. Oh how come they're not
16:49
merging? Okay. Yeah. So that's an issue.
16:52
how much it took. Almost 5 hours. Like
16:55
not going to lie. Right. So, there was
16:57
three prompts, core, visual, some
16:59
follow-up prompts, and you can see still
17:01
not fix it. Well, that's definitely not
17:03
the best test I did. Now, maybe I was
17:06
prompting it bad. Let me know in the
17:08
comments. Of course, you're going to see
17:09
the prompt history on the screen as
17:11
well. And if you take a good look on the
17:13
chat history, you can see that it has
17:16
the access to do the screenshots, review
17:18
itself, which is actually great. This is
17:20
how it's supposed to be ideal with a
17:22
gentic approach. But not only it see the
17:24
screenshot but in runtime it also can
17:26
get idea about some values what's
17:28
happening in the game because yeah not
17:30
only images gets useful information.
17:32
Then here it was but again like the time
17:34
I want is significant. Let's do one more
17:36
test. Let's do the next test. How about
17:39
we try to do a nav mesh right? It should
17:43
be possible again. Like, but before you
17:46
actually had to set that through some
17:50
tools and stuff. So, how about it's been
17:52
a while. I've been not looking into this
17:55
one, not going to lie. So, the chest is
17:57
simple. It's a tower defense and there
17:59
are enemies that goes by pass, right?
18:01
Prompt is on the screen. Let's take a
18:03
look. Okay, so basically can place
18:07
cannons by pressing one, two. Okay. Then
18:11
and then we earn gold. Okay. Okay. Okay.
18:13
Okay. Then we can press a cannon. Let's
18:15
see how cannon works. Guess we're going
18:17
to need to wait. Cannon damage is a bit
18:20
weird, right? Okay. Yeah, I think hit
18:22
points like definitely need some work on
18:24
that. All right. [music]
18:26
But enemies actually finding their way
18:28
quite nicely. I think the balance here
18:30
is awful of course, but you can see even
18:33
though like I did not explain anything
18:35
except like the visual way like how
18:38
location should be represented, it
18:40
figure out the shortest path. Well, part
18:42
of this task I think it accomplished,
18:44
but definitely need to work on the
18:46
balance. Altogether, three prompts
18:48
almost 4 hours, 455 model calls, and
18:52
potential $14 spent. And let's do the
18:56
final test. And since that's the final
18:58
test, let's make it cool. [music] And
19:00
what can be cooler than fireworks night?
19:02
So the tasking on the screen, we do have
19:04
sort of water lake, basically something
19:06
reflective. And we do have the
19:08
fireworks, right? Let's see how good it
19:11
will be. Okay. So fireworks, they are
19:16
not that bad, but I don't get one thing,
19:18
right? It's not a real reflection
19:20
because you can see particles both here
19:23
and here falls down. So, is it like a
19:26
duplication or is like what? Well, it's
19:28
not a reflection really, right? I don't
19:30
get it. It looks a bit weird, but the
19:33
fireworks themselves. Well, I think it's
19:35
not bad. Look, I think it's quite cool
19:36
actually. Okay. Yes, something wrong
19:39
with the reflection for sure, but
19:41
overall looks super cool. And the
19:43
firework took quite a while. Well, but
19:45
basically that's because I was actually
19:48
setting this to work at night and I had
19:50
to resume it at some point. And as you
19:53
just saw, it was also made in Unreal
19:55
Engine and it took quite a while. It
19:59
there was like three editor crashes. I
20:02
set it to work at night and I come up
20:03
and see like what's going on. like they
20:05
basically crash it the Unreal Engine, do
20:07
some circles and yeah, I guess like
20:11
Niagara FX like was very difficult to do
20:14
or like they were crashing the memory or
20:17
at some point it was not optimized
20:19
whatever like but again like look look
20:21
at the numbers like definitely not that
20:23
fun as Unity. Anyway, that was it.
Final Verdict: Is Unity Now the Best Engine for AI?
20:26
Please let me know what you think about
20:28
the test or if you have any ideas about
20:30
the test. I'm going to definitely use
20:32
them in my next videos. That was Steph.
20:34
Like and subscribe and see you in the
20:35
next
