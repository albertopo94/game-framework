My agent workflow
0:00
It's recently come to my
0:01
attention that not everybody is using AI the same way
0:05
that I am. So today I wanted to share with you the ways that I'm
0:09
seeing a lot of value coming out of AI usage and what I think that
0:12
you should do especially if you're already a developer and it's
0:15
something that you're trying to experiment with and you're trying
0:18
to figure out how you can make good use of it.
0:20
So the first thing is that I've noticed a lot of people are
0:24
still kind of doing things the old way and if you're not doing that
Stop copy-pasting code
0:28
you can skip ahead. But if you're copying things out of
0:31
some application or you're writing you know little
0:34
questions here and then copying and pasting answers
0:38
back and forth well that's how AI stuff worked I
0:42
think four months ago or nine months ago.
0:45
Nowadays you should definitely be going a fully agentic route in my
0:48
opinion which means that you should be using a harness like
0:52
the simplest ones are Claude Code and GPT Codex.
0:56
You can run some other ones or run your own local ones but that's
1:00
the other thing that I want to talk about which is that
1:04
a lot of my friends were and still are running some
1:07
smaller local models and trying to really optimize
1:11
for minimum token usage and I think that they're well I
1:15
know that they're really targeting the wrong thing they're
1:19
trying to optimize for a potential price that may come in the
1:22
future
1:24
sometime down the line which is probably realistically never going
1:27
to happen instead of taking advantage of the price that we already
1:30
have right now and what I mean by that is that instead of
Subscriptions and API-equivalent value
1:34
trying to like maximize their usage or maximize their token
1:38
value by running these small quantized local models or
1:41
something what they should be doing is just jumping on to either a
1:45
Claude right now is probably what I recommend a Claude max plan
1:49
or a GPT max plan and on these depending on the
1:53
budget they should be jumping up to probably the $200
1:57
plan depending on how much they're doing and when you look at it
2:00
if you look at the amount of actual compute that you get off of one
2:04
of those plans compared to the amount of compute that you're
2:07
getting off of the
2:09
API value of stuff it's not even close now if you're
Make the tools pay for themselves
2:13
thinking that seems crazy and expensive it definitely is but what I
2:17
would recommend is that you just make it pay for itself and
2:20
I've done that myself I actually made it so that
2:24
Claude well I put Claude on a couple different tasks one was
2:28
finding any extra recurring things that I didn't know about and
2:31
found quite a few of them that it canceled automatically it
2:35
canceled the gym membership that I hadn't used it had no way to
2:38
cancel online it got me a big refund from State Farm when it
2:42
realized that they hadn't canceled something else a year ago and
2:46
it saved me way more than it's cost me I also had it build me a
2:49
new application for recording this so that I wouldn't have to keep
2:53
paying a $50 monthly fee to record stuff so it's not too
2:57
difficult if you have anything that's kind of a recurring cost
3:01
in your house that's not a streaming service to have it just kind
3:05
of help wipe some of that stuff out and I definitely recommend you
3:08
just do that for the month and then experiment with it and see what
3:11
kind of stuff that you can build now if you're using Claude here
3:14
are the settings I would recommend put it to Opus you want to
Opus and effort settings
3:18
use the latest Opus model on the second highest
3:22
effort setting don't put it to ultra code
3:26
unless you're ready to just kind of have it go crazy
3:30
and when I say I mean like if you put it on ultra code you're going
3:33
to have it build something really awesome with really great
3:37
results it'll think for a very very long time do a whole lot of
3:40
work give you something cool but it's going to also burn through a
3:43
lot of your usage in fact um earlier this week on Monday my usage
The RTS prototype and one dedicated server
3:47
reset I told it to build me a Command & Conquer: Zero
3:51
Hour clone that supported way more players and
3:55
ran on Steam's networking so that it wasn't lockstep
3:58
and um was somewhat fun and a little bit unique but
4:02
not worry about the art just get the full gameplay working four
4:05
hours in it kicked up the first test and another four hours
4:09
later it had basically a full working eight versus eight
4:13
multiplayer game with full networking all there so you can get a
4:17
lot of stuff out of ultra code mode but it burned through 60% of
4:20
the usage for the week so it's kind of a big trade-off that's not
4:24
where I would start though what I would say is start on the Opus
Design before implementation
4:27
model put on the second highest level and then begin with
4:31
design so tell it that you're ready to design a game you want to
4:35
design or write a design doc or build a design doc or if you
4:38
already have one even better give it your design doc and tell it
4:42
that you have a design doc and you want to work with it on the doc
4:45
have it ask you questions about the game design that you want to
4:48
make first give it as much info as possible about it and then have
4:52
it ask you questions about it follow up questions and answer as
4:55
many questions as you can then once the design looks good that's
4:59
when you start implementing it now before we get on to the
5:03
implementing it part giving it the design if you don't already have
5:06
a design doc written out don't just sit there and write one
5:10
out instead pull up your microphone
Talk through the design
5:13
grab your phone something else and just talk through the entire
5:17
thing tell it everything that you want in the game all of the
5:21
details and just talk through it as much as possible give it
5:25
you know all of your random little things that you're thinking of
5:28
and edge cases and so they're talked for like 10 15 minutes if you
5:31
have to that's what I've done before give it as much info as
5:34
possible and then once the questions are done you'll get to the
5:37
point where you can actually kind of have a working design doc and
5:41
a plan for how to implement it that's what you'll have it build
Project setup and Unity tools
5:45
create a new project create a new folder for all of this stuff that
5:48
you're going to create your project and your game in and then
5:52
have your agent create a new folder with a new game
5:55
project underneath it using whatever engine you want to use I would
5:59
recommend using Unity from what I've seen it works the best with
6:03
AI stuff I've tried the others and they're okay but it
6:07
seems like the agents just are better trained for Unity stuff which
6:09
makes sense because there's so much Unity info out there and there
6:13
has been for so long it had a lot of info to train on and what I
6:16
would also do is tell it to use Unity skills Unity released some new
6:19
skills that allow you to do some really easy game creation like
6:23
project management stuff right from the AI agent just tells it how
6:27
to do it so tell it to use Unity skills create the project
6:31
and start building it and tell it to implement the game or
6:35
build the game until it's got a working playable demo and then
6:38
present you with the demo then once that demo is there that's when
Playtest, report, iterate
6:42
you start deciding how you want to iterate and in my case I've
6:46
already done one video on one of the iteration tricks that I
6:50
use with a little pop-up I'll I'll link that here using F10
6:54
and I've got another one that I'm going to show pretty soon we've
6:57
kind of extended on that and made it even easier to use and a
7:00
little bit faster I kind of want to talk about Chris's TikTok
7:03
driven development sometime too if this kind of stuff is
7:07
interesting you got questions about the process and what happens
7:11
next just drop a comment down below if you want to see more of
7:14
these obviously hit thumbs up and all that stuff and if you're
7:16
building something cool let me know what that is down below too I'd
7:19
love to kind of pop some of these things up and share what
7:21
everybody's making all right see you later bye
