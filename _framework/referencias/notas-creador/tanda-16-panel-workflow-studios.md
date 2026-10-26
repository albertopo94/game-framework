Game Developers Show Their AI Workflow
Coming up: game design revisions in hours, not weeks?
0:00
How long did that take you to refactor everything and send it off again?
0:04
Maybe an hour or two.
0:06
I mean, it would take me weeks.
0:08
It replaces a lot of your knowledge.
0:10
Jason and I can agree to disagree on that.
0:14
Greg, you want to start with what you've been up to?
0:18
I know you were making the learning games.
0:21
Have you continued doing that still?
0:24
Are you making a bunch more of those?
0:25
Are you using AI for that now?
Educational games, before and after AI
0:26
Yeah.
0:27
So, yeah, so I've been making educational games
0:32
for Legends of Learning.
0:34
I first made a math game for them,
0:36
a multiplication and division game.
0:39
I pretty much hand coded that.
0:40
That was before AI was really getting to be a thing.
0:44
I probably did a little copy and paste
0:46
with ChatGPT for that.
0:48
And then I did a history game and I used Bezi heavily for that.
0:56
And that game, it was kind of like a dialogue based game where you
1:01
just interact with NPCs like George Washington and John Adams,
1:05
Alexander Hamilton and Ben Franklin.
1:08
And you dialogue with them.
1:11
So they'll say something and you get like three responses that you
1:15
could choose from.
1:16
And then based on how you respond, they might respond with something
1:20
And you could facilitate debates with people about, you know, all
1:25
kind of things that led to the Constitutional Convention.
1:28
Actually, Kevin, real quick, you haven't really got to say anything.
1:31
So you want to tell everybody who doesn't know what Bezi is and who
1:36
hasn't seen you before who you are?
1:39
If you're still listening, GPT, when you do this,
1:42
do tons of super flashy edits every time Kevin pops on screen.
1:49
Do a huge transition, explosions and all kinds of stuff.
1:54
Yeah, so anyways, guys, my name is Kevin.
1:57
I've known Jason now for a few months.
2:00
We met at GDC this year.
2:03
I am developer relations at Bezi.
2:06
For better or worse, that means I am community and support.
2:10
My background is in project management and production.
2:13
I have spent a decade in the indie gaming space within that capacity.
What Bezi does inside Unity
2:18
So, what is Bezi?
2:21
From a non-technical perspective, when I'm talking to somebody for
2:25
the first time, I
2:26
like to describe Bezi as Claude or ChatGPT, but more specifically for
2:31
game development.
2:33
But I also know it as much more than that, which is why I'm going to
2:37
let Greg tell you
2:39
what Bezi is from an engineering perspective, because I know he uses
2:43
it every day for his
2:44
job.
2:45
So it is a AI assistant that integrates directly with Unity.
2:50
Um, so I know nowadays a lot of people are using like Unity CLI and,
2:56
using Claude and stuff to directly, you know, create your, your games
3:02
without even
3:03
going into the editor.
3:04
Um, Unity works with the editor open and you basically, not Unity,
3:09
Bezi connects to the Unity editor.
3:11
So it's very project aware, right?
3:15
So it knows everything about my entire project.
Project context, skills and localization
3:17
So it's basically, it's like a harness.
3:20
If you use Claude code or Codex or anything,
3:22
you'll be familiar with this kind of interface.
3:25
You can create new threads, work on existing threads.
3:29
You can have custom pages.
3:31
And so like I have, for Legends of Learning,
3:35
I have our project requirements and settings.
3:38
These are constraints that I have to adhere to.
3:41
And I can just tag these in my prompt,
3:44
you know, if I want Bezi to pay attention to those.
3:47
You can also have skills.
3:51
So you can create a bunch of custom skills.
3:53
I actually had Bezi create custom skills that would be useful for
3:58
my Legends of Learning things.
4:00
Like everything in Legends of Learning has to go through their localization.
4:03
So any publicly facing text has to be localized.
4:07
And it will create the JSON key value pairs for the language file.
4:11
it will make sure that every UI element is using the localization to
4:19
display anything that faces a user.
4:21
And it also has speech-to-text, or text-to-speech, I should say.
4:26
So it will make sure that it uses the language key,
4:29
not just for what's visually displayed,
4:31
but for everything that would be spoken to the user.
4:35
You can also create sub-agents.
Prototype the mechanics before implementation
4:37
I can tell, for instance, if I wanted to create a prototype for a
4:44
mechanic,
4:45
right, so I have a skill that uses the built-in Bezi skill that
4:50
creates proofs,
4:51
and I'll show you proofs in a minute, which is basically like a web-based
4:54
prototype of whatever it is you're designing.
4:57
So I actually created a skill, this educational mechanic prototyper,
5:02
that will build a proof using Bezi's create proof skill.
5:10
And then I can actually just have Bezi implement that proof in Unity.
5:18
And I use this to create mockups.
5:20
So basically, I don't do anything by hand anymore.
5:25
So I fed Bezi some game design ideas for a learning objective, right?
5:33
So I wanted to do a game on plate tectonics that meet these learning
5:39
objectives, these core learning objectives and then peripheral
5:44
learning objectives that the game has to teach the player through
5:48
gameplay, right?
5:50
And I basically had Bezi create using a Google MCP server.
5:56
It created this game design document, right?
6:01
Based on the game ideas I gave it for, and I, and I gave us different
6:06
ideas and I had them use some for different levels and some for mini
6:10
games and it.
6:11
The learning objectives come from Legends of Learning.
Design around real constraints
6:14
And I told Gemini, give me 10 ideas for a game.
6:21
And I gave it the other requirements and limitations, you know, the
6:26
technical requirements.
6:28
Like the uncompressed build size has to be less than 30 megabytes.
6:32
It's a WebGL build.
6:33
It has to run well on low-end Chromebooks.
6:35
It can't have drag and drop, you know, things like this.
6:39
I gave it all that and I told her, give me 10 game ideas that would
6:43
allow the player to learn these concepts through gameplay.
6:48
Okay.
6:48
and they can't just click through the game.
6:51
It can't just be lectures or quiz-based.
6:53
It's got to be a way.
6:54
They actually have to play something that teaches.
6:57
And it gave me different ideas.
6:59
And then I picked ones that I liked,
7:01
and I gave them to Bezi,
7:04
and I said, create a game design document
7:06
where these concepts, these game ideas
7:10
are implemented as levels and mini-games
7:12
with these constraints and so forth.
7:16
And so it built.
7:17
four levels and four mini games.
7:21
But it, Bezi wrote this whole document.
7:25
Now these mock-ups, they're screenshots from the proofs that I had Bezi
7:29
create, the prototype proofs, right?
7:33
And I just pasted in screenshots as part of the GDD.
7:36
And I went through about four rounds.
Four rounds of feedback
7:39
So I went through about four iterations where they came back and they
7:45
gave me feedback, things they didn't like and things they wanted me
7:49
to address.
7:50
And I just told Bezi, you know, help me respond to this feedback.
7:57
You know, how can I change it to address these concerns?
8:00
And I had to rewrite that section of the game design document.
8:03
Then I had to refactor the proof for the prototype for that.
8:07
And then I generated new mock-up screenshots and sent it to them for
8:13
review.
8:15
So that's how I did all of that.
8:18
How long did that take you to refactor everything and send it off
8:22
maybe an hour or two.
8:26
Like an hour or two.
8:27
Okay. And what do you think, how long would that have taken before
8:33
Oh, gosh, forever.
8:41
I mean, it would take me weeks.
8:43
And here's the thing.
8:43
Once they approve, and the game design document, the reviewer just
8:47
replied today and said that their concerns were addressed and this
8:50
game design document is ready to go.
8:52
So now I'm guessing on Tuesday, since Monday's a holiday, Legends of
8:56
Learning is going to send me an official acceptance saying, okay,
8:59
your game design document's been approved.
9:01
You have 10 weeks to deliver a game.
9:03
Now with Bezi, and I already have most of this prototyped, I'll have
9:08
a fully functional game within a week probably that I can spend the
9:13
other nine weeks iterating on for optimization, polish, adding some
9:19
juice.
9:25
Yeah.
9:26
And they were going to get a much better game than I could have
9:30
delivered just as an indie
9:32
developer with no staff.
Does experience still matter?
9:34
The one thing I'm going to add to this conversation right now, though,
9:38
is both of you are experienced developers.
9:42
So please, if you're watching this, understand that Greg already
9:47
knows what he's doing and he's using AI to accelerate his workflow.
9:52
That's very different from somebody with no experience touching AI
9:56
for the first time to try to make a game.
9:59
So it's useful to everybody.
10:02
But one of my favorite sayings when I'm providing support to people,
10:06
or I'm just talking to anybody about AI, especially those who are
10:09
worried about losing their job, the more you know about what you're
10:14
doing, the better AI is to work with for you for that specific task.
10:20
It doesn't replace your experience or your knowledge.
10:23
It never will.
10:24
It replaces a lot of your knowledge.
10:26
Not, I didn't say fully, but it replaces a lot of your knowledge.
10:30
A lot of the stuff that you used to need to know, you no longer need
10:34
to know.
10:35
oh okay well jason and i can agree to disagree on that i don't think
10:42
going to fully replace people i still think knowledge and experience
10:45
is going to matter
10:46
But I did a video recently mentioned that my nine year old was able
10:52
to make his own Roblox games.
10:54
I did not help him.
10:55
And then he figured out how to make his own game and shared it with
10:59
friends and had other kids in there playing with him.
11:02
He was building stuff and having fun.
Building is fun again
11:03
So I know a lot of people are concerned, especially people that they
11:08
feel like their job is programming and they love writing code.
11:12
But I was telling, you know, I'm having more fun now than I've had
11:18
since I first learned a program in 1984, writing games.
11:26
Right.
11:29
- Yeah, and when I first realized
11:31
that the computer was doing what I told it,
11:33
that was like a light bulb went off in my head.
11:36
I'm like, this is what programming is.
11:37
Well, and so, you know, at my day job, I'm expected, my job, my job
11:43
is to deliver reliable software that provides value for the customer.
11:48
Right?
11:49
My job is not architecture, it's not design, it's not writing code,
11:52
it's not testing, it's not optimizing, it's not documenting.
11:57
My job is to produce software that provides value for the customer.
12:02
All those other things are just tasks that are part of my job.
12:07
And to the extent that I can automate those tasks with whatever tools
12:11
are available, I'm a much better employee, a much more valuable
12:18
employee for my company.
12:21
And I'm delivering much better value for the customer than I
12:25
otherwise would have.
12:27
That's one of my biggest talking points when I'm talking on Reddit.
12:36
For those who don't know, I help moderate r slash game dev.
12:41
It's the largest subreddit for game development on the platform.
12:46
So whenever a conversation comes up about AI and employment,
12:51
all I'm really asking people to do is be aware of what it means for
12:56
their career
12:57
to not educate themselves on what this new technology
13:02
and these new tools are capable of.
13:05
Because if you aren't adapting to the new technology
13:09
being introduced into your field of work,
13:13
you're going to be replaced by somebody who did eventually.
13:17
you should be exploring and figuring out how AI can be applied to
13:22
your job
13:23
and how it fails at contributing towards your job.
13:29
Because AI can't be used for everything.
13:32
And it's up to you to kind of figure out where it can be used.
13:36
And I think that's where a lot of studios are right now in terms of
13:39
their pipeline,
13:40
is they're exploring all these different uses of AI and where it
13:43
makes sense and where it doesn't.
13:45
where is it actually saving their team time
13:48
versus where is it actually just creating friction?
13:51
Like there's a lot of nuance here
13:53
and people are still exploring that.
Team workflow and human responsibility
13:55
I mean, I'm part of a team and we have a sprint board.
14:00
I don't write user stories anymore, Claude does.
14:04
I basically, I have a spec plan for whatever feature I'm working on,
14:09
and I interact with other teams that I'm developing this for.
14:13
And as I get requirements, I basically have Claude keep a series of
14:17
Confluence documents up to date with where we are in this process,
14:21
what's been done, what's still to be done, where I need answers to
14:24
questions, all these things.
14:26
And whatever work I need to do, I tell Claude to create stories,
14:31
assign them to me, and then move these into the sprint.
14:39
And then I tell it, okay, start implementing this story.
14:41
It creates a branch.
14:42
It starts coding.
14:44
It moves that into in progress.
14:46
It adds evidence to the story, moves it to testing.
14:50
You know, it will give me a diff that I can take up to our higher
14:54
environment and deploy it and test it.
14:58
And then I can, if there's any bugs, I can just bring back what the
15:01
bug was.
15:02
Claude will fix it.
15:04
You know, and it will move it to done and put all the evidence in the
15:06
story.
15:08
And it will update the Confluence document.
15:10
Here's where we are now.
15:11
here's what's still left to be done.
15:13
And then at the end of the week, when I have to give a status report,
15:16
here, give me an
15:17
executive summary of everything I did this week.
15:20
Here's what I'm going to be working on next week.
15:22
Here are my impediments.
15:24
I don't write any of that.
15:30
I'm responsible.
15:33
So like whenever it does fix a bug, you're testing it to make sure it's
15:37
good.
15:38
Yeah, but see, you're still in control.
15:41
I still think this all comes back to the fact that the three of you
15:45
are just so experienced.
15:47
You know what finished means and what a good output is.
15:51
So, yeah, like I understand you guys being orchestrators and doing
15:56
all this super amazing, cool stuff with AI.
16:01
Just from the perspective of watching a lot of indie developers start
16:07
adopting these type of tools, they don't have your skill set.
16:12
And they do struggle a lot with staying in control.
16:16
And I feel like they hand too much control over to AI without verifying
16:21
that it's executing what they actually need.
16:25
And they run into problems.
16:27
Yeah.
16:27
I mean, and I think it's interesting to talk about like, what does
16:30
your process look like, Greg, when you're working on the game?
16:34
So once you got it into Bezi, like you got your game in there, you
16:39
got the design done.
16:40
Like what's the next actual step?
16:42
I think we kind of never got to that part.
16:44
We got distracted with the fun stuff.
From a design document to a resumable plan
16:47
yeah um basically what i would do is i put Bezi in plan mode and and
16:57
i was using um
17:00
Opus 5.5 high right so i would come down here and i would pick
17:06
Claude Opus 5.5 on high um and i actually i was initially i had a
17:12
problem connection
17:14
or connecting to my Google Docs.
17:17
So I fixed that and then after I fixed
17:20
the Google Docs connection using Bezi to help me fix it,
17:23
I then told it to just reproduce my game design document
17:27
in a local page here.
17:29
So this is my game design document reproduces a local page here in Bezi.
17:34
So then I told it.
17:41
I told Bezi and plan mode to build an implementation plan for it.
17:51
This is the new plan for this game, right?
17:56
And it breaks it up into phases.
17:59
And it's adhering to all of my, you know, my rules, first of all, but
18:05
also those things like the project requirements and settings,
18:11
legends of learning architecture and best practices based on using my
18:14
existing games as a template.
18:17
I put together these architecture layers and rules that I wanted to
18:20
apply for how I want everything to work.
18:24
And so it also creates a to-do list that it will operate against,
18:30
right?
18:33
And then I can just tell it, you know, I can at any point stop this
18:39
and then resume the plan with where it left off.
18:42
And then all I got to do is go start to test it and then give it
18:46
tweaks, things I wanted to fix and stuff.
18:50
When you're doing the design phase of stuff, do you ever have have Bezi
18:56
just ask you questions or whatever AI you're shoving into?
18:59
As part of the plan, when it's in plan mode, it will pop up and ask
19:03
me different questions about, you know, how would you like me to
19:06
handle this?
19:06
And would you like this to work this way or that way?
19:08
Give me like three or four choices.
19:11
And once I answer all those, then it will go off and work.
19:15
I'll also add that depending on how you prompt, you can tell it to
19:19
ask you more questions than it otherwise might. So if you have more
19:23
uncertainty, you can definitely ask Bezi to take a deeper dive and
19:28
ask more questions.
Opus orchestrating, Sonnet coding
19:30
So I created a sub-agent. I actually told Bezi to create me this sub-agent
19:34
using Sonnet 5.5 because Haiku is not available yet in Bezi.
19:46
And so now I tell Bezi to use this sub-agent for coding tasks when
19:52
building the plan.
19:56
And so it's applying all of these rules and validations and
20:01
boundaries and everything. And so when it was building the plan and
20:04
implementing the plan, it used this subagent, which was using Sonnet
20:09
5.5, but Opus 5.5 was orchestrating the whole thing from above.
20:14
Are you seeing a measurable cost difference there?
20:19
Because I've wondered a lot if having a smaller agent do stuff makes
20:25
sense
20:26
when the bigger agent still has to pass that stuff back and forth.
20:29
Are you really saving much there?
20:31
And does it do a worse job and have to iterate more?
20:35
I can't answer that question because this is my first time doing this.
20:41
Yeah, I don't know.
20:42
I'll also say when it comes to the cheaper models, if you want to get
20:47
good results, particularly with coding tests, they have to be scoped
20:51
appropriately.
20:52
Like they aren't going to be able to execute a very complex system.
20:57
But I imagine Greg has it broken down to such small pieces that it's
21:03
able to execute quite well.
Testing on another machine and network
21:06
have um when you said Macs i've got a mac mini sitting right there
21:11
next to my desktop um and
21:13
it's just there to run um more ai tests so whenever i'm building
21:17
anything that's multi-user or like
21:20
multiplayer um even like this recording app what it does is it
21:24
launches a version of it on that mac
21:26
and then it connects it and it typically i have this iphone here it's
21:31
literally just for tethering
21:32
on a cell connection and finding my wallet, which I lose all the time
21:37
in my wallet and keys.
21:38
But it uses that connection so that it can test across different
21:42
networks, not beyond my home network and does all automated.
21:45
So I just have Claude and ChatGPT both set up on there.
21:49
And then this system has a direct connection to those ones.
21:54
And then it just directs them to do whatever testing it needs from
21:57
them.
21:58
So it'll just kick it off, tell them to do testing.
22:00
Or if it wants a Mac build, it'll just request a Mac build from those
22:03
agents and get a build back.
22:05
What's this game we got pulled up here?
Greg's playable Word Board experiment
22:06
So my wife likes to play Scrabble Go.
22:10
And she had mentioned she doesn't like all the ads that she has to,
22:16
you know, wait through to play.
22:19
And so I thought just for a fun experiment, I'm going to ask Bezi to
22:24
create me a Scrabble Go clone.
22:26
You can play single player against bots of configurable skill level.
22:31
And I wanted the ability to load and save games.
22:35
Oh, and I gave, I created an empty Unity project,
22:40
and I dragged in like a GUI Casual Pro UI, you know, asset pack.
22:48
I copied in some music and sound effects that I already had from the
22:52
asset store.
22:54
And I told it, you know, using these assets, build me this game.
23:00
And so it created this and you can zoom in and you can drag and AI is
23:09
amazingly good, unfortunately.
23:11
How did she like the game, though?
23:13
Yeah, she's used to the other one.
23:18
I mean, she liked it, but she's used to the other one,
23:20
so she doesn't really play it.
23:21
But I mean, it was a fun experiment.
23:23
So I did tell Bezi that I wanted it to be a WebGL game that could
23:28
play on an Apple iPhone without having to be an iOS build.
23:34
There's a little toggle for I added mobile controls.
23:40
So as long as that was turned on, it worked on the iPhone.
The iPhone bug and the follow-up fix
23:44
The initial build that Bezi gave me didn't work. I mean, it worked
23:48
except drag and drop didn't work on the iPhone. It worked in the
23:52
editor and it worked in a browser, but it didn't work on an iPhone
23:56
browser.
23:57
And so I just described the problem to Bezi and said, oh, we need to
24:01
create a custom WebGL template, add this to the template, and it'll
24:06
work.
24:07
And I did, and it worked.
24:08
And then there were scaling issues I had to tweak.
24:11
But I mean, it was almost a one shot, not quite a one shot, but
24:15
almost.
