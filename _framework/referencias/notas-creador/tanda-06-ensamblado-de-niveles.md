0:00
With the best AI tools, how difficult it is to create a nicel lookinging 3D game
0:05
level? Is it just about generating pile of assets and drop them into game engine? And if you try to ask AI to
0:12
place them around, most likely you will end up in slop. However, if you use them rights in right workflow, you're going
0:19
to get amazing results like myself. And in this video, I'm going to break down this complete AI workflow and I show you
0:26
how to do that only using free AI tools. So, the starting point is of course the
0:32
idea. And I actually have something amazing prepared for this video. We're going to create this amazing pirate
0:39
cave. I just like everything about this idea. I was actually checking your comments and then I tried to do some
0:45
ideas and this just pops up and like wow. And there are a few difficult things to address here like at this big
0:52
cave and a lot of interesting objects. So what will be the next step? High level it looks like this. First we're
0:59
going to prepare building blocks that includes props concepts generation and
Concept Splitting and 2D Asset Generation
1:04
preparing them for further work. Second we actually convert this asset kit into
1:10
the game level and we're going to do that in Blender. And it's not about modeling. It's more about assembly
1:16
things. You can also do that in game engine, but you're most likely going to spend much more time. And third step is
1:22
to set it up in game engine. For this video, I'm going to show it in Unreal Engine, but same thing can be done in
1:28
Unity. Now, let's follow the plan. So, here's how you can do that for free. There is AI studio from Google where you
1:35
can access free nana banana. And guys, it's still amazing. I've been doing so much tutorials using that and hopefully
1:42
it will be soon updated and do even better job. Of course, if you have some bugs, you can use better models such as
1:48
Nano Banana Pro, GPT image to edit and so on. And here's what [music] I did. Basically, I split my concept image into
1:57
smaller chunks and from those smaller chunks, I extracted building blocks. For
2:02
example, with the cave, I extracted the cave alone. And then I actually circle it on the image. You can actually do
2:08
that right away in Gemini and said, I need this and this and this stone. Then I got some generations and selected the
2:15
best ones. Same thing I did with the peers. Again, just go around and say
2:20
like, okay, I need this part, this part, this part, this part. That's the whole magic. And this is very important
2:27
process. You might need to do this process once or two times to get better
2:33
understanding at what size you can keep it or where it actually makes sense to go deeper and generate it in smaller
2:39
parts. For me that's the question about how much control over scene I want. So I
2:45
generate them like that. How I going to actually place them around? Also for some objects like stone, boards, planks,
2:52
I generate them in group and later I going to generate them in 3D as well. That saves a lot of time and tokens. And
2:59
one more thing I also prepared with Gemini is textures like this fishnet texture or later I even show you how to
3:06
create seamless texture to use as materials. And here's how my final list of images look like. Nothing crazy.
3:13
Again, depending on the environment, this list can be like three times more. That's totally fine. And one more wise,
3:19
you don't really need to predict all parts you may need. You can always circle back to generate 3D models. We're
Creating 3D Models
3:25
going to go to Hunion website. They still provide with 20 free daily generations, which is amazing. [music]
3:31
And there's basically two options how you can address that. First one is to generate high poly. And I recommend to
3:37
use that for some big objects where you want to keep those details. And I going
3:43
to do that for most of the stone objects. You can see them on my screen. And I don't even need a texture because
3:50
I'm going to show you one cool approach how we're going to bake normal and add seamless texture on top. Another thing
3:56
is that if you go to laboratory, there is 3D mods topology which generates low
4:01
poly meshes. It use same credit pools and basically you can choose triangles or quads here. There's also amazing
4:09
Hunan 3D studio. I made a complete video recently. It's on my channel. There are
4:14
even more possibilities and also for free. Now for most of the simple objects
4:19
I was actually using smart topology and I was getting quite quite good results
4:24
which you can see on the screen. Again, how do you decide where you need more details, less details, is how close
4:30
players will see those objects. And to be honest, even though it's low poly, there are quite enough details. But if
4:37
you want to get maximum from what 3D AI can offer, I definitely recommend to take a look into Tripa P2, which just
4:44
recently released, I think two weeks ago. As soon as it released, it actually took first place, basically surpassing
4:51
itself. Also, Tripo still takes first place in high poly generation. Main new
4:56
feature is that they added quads and again like the quality of topology is
5:01
insane. It still requires thinking and same as with Hunion again like you do something with high poly first then do
5:08
topology baking something you do with low poly right away. Again, very similar approach that you see in the video, but
5:14
overall you're going to have better mesh quality, less time to process it and so forth. And of course, by my link in the
5:21
description, you're going to get extra free credits. And if you decide to buy subscription, there will be a promo code
5:27
for 60% off first months. Now, back to cooking. Now, let's bring it all to
Fixing and Refining Textures
5:32
Blender. Why Blender? Because that's free software. It's very convenient, and you don't really need to learn
5:38
everything about Blender. You just need to know some tools to be able to process that. Whether that's high poly, low
5:44
poly, whatever. I think that's just the best tool to work with 3D. and even myself I can't remember when last time I
5:51
was doing actual modeling. So what we are going to do now is to convert these assets into actual building blocks.
5:58
There are a few issues that might be concerning you. Let's start one by one. First I'm going to prepare some assets
6:04
from textures that I generated which was that pirate papers. As you remember I generated color texture and alpha
6:12
texture. And here's [music] how it's done in Blender, right? You can prepare it here to place it around and later
6:18
again like reuse it in Unreal Engine. This is what exactly what I do. I created one plane, one texture for four
6:24
and I just going to split this plane into four parts. Why? Because these four papers will use one material while there
6:32
will be multiple objects. I also going to do that for fishnet. You can see it here. And now I actually went through
6:39
all my objects and selected those I'm not happy with in terms of texture right
6:44
we talking about like just texture in first place so there will be some boxes
6:49
anchor barrel and what I going to do I'm going to select all of them and export
6:54
them as GB and bring you know where into the motive motive is still available for
7:00
free and by my opinion this is like a best tool for AI texturing and all I
7:06
have options to only use pay tools but still we use modifes.
7:11
This is how good it is and the process here look very simple. We select the object import all objects so you can
7:17
actually traverse through them. Now we're going to go to texture mode and here you can see on the other side of
7:23
the coin is completely broken. So I preliminary uploaded all assets here. You can just click plus and upload all
7:30
the images. I choose in painting painted the broken area and with selected view
7:36
click in paint or generate. Now there's generated image and I can simply use
7:42
this in paint to reveal that area that I want to change on my texture. That's how
7:48
simple it is. I just fix it this texture and I can actually export back this
7:53
color texture and use it back in Blender. Here's another case. I have this box and you can see like the front
8:00
side looks very nice but the sides look terrible like I mean less detail like I
8:06
mean basically it doesn't fit in style. So let's regenerate it and boom. So this
8:11
one looks so much better. I'm going to do that for other sides as well. And now
8:16
I'm pretty happy. Let's do the same thing for anchor. But in case of anchor I'm completely unhappy with texture in
8:22
general. So I'm going to actually hide that texture. Select the reference and generate completely new image. And
8:28
there's another tooling here is that you can add it as layer. And you can see how
8:34
much better this texture is. Add as layer sort of like print the complete
8:40
texture from the view. So you can basically go view by view and again generate make sure that it generates
8:47
what you want otherwise like specify the prompt the prompt image and do the thing. So here you go. Like it's much
8:54
better job that it was originally done by Hunan. And good news for you guys, of course, there is complete breakdown on
9:00
how to use motive on my channel. So it's good for two cases. Address some artifacts, add some details, text,
9:08
logos, I don't know, whatever. Just make anything sharper or even retexture the
9:13
object completely. That's also possible. Now when all my objects ready, I can just export the color texture for each
9:20
or export them all at once. Go to back to Blender and for example, I'm going to just simply replace the color texture
9:28
for new one from motive. One potential issue fixed. What else can go wrong? Sometimes there are very very small
9:35
artifacts on textures and to do this round trip with motive might be taking too much time. For this one, I can
9:41
recommend you to take a look into some Blender native functionality such as clone brush. So, it works very simple.
9:48
Go to your object, click on the texture that you are not happy. Let's say color texture. It must be selected. Now, go to
9:54
texture paint mode. And here's what you can do. Select the clone brush which is here. And with control, click anywhere
10:01
to source the texture. And it works like this. Basically where you click with control it will use that as reference to
10:09
clone that area. So you see like let's say there is like some holes and I don't need those holes. Look I click somewhere
10:16
and I just like painted like that. That's it. I saved so much time. I can just address some issues. There can't be
10:22
some blurriness that you can address like that etc etc. And you might only see that when you can start assembly
10:28
objects and more. One thing if you do any modification of texture in Blender don't forget to save it. So you can do
10:36
that like this. Another extremely common issue when you work with AI generated assets they are not consistent by color.
Color Correction, UV Unwrapping, and Baking
10:42
Let's say we have these two boxes. Let's say I'm happy with the texture overall
10:47
but I want them matching in colors. So I want the left one look more like the
10:52
right one. And here's the easiest way I figure out for myself. In Blender right here we can do the color correction.
10:59
That's very easy. Shift A or right click and you can get access to a bunch of
11:04
color nodes that you can connect between color texture and the material input and
11:09
just do the correction. So I played a bit with val and now I have much better result. Again there are plenty of nodes
11:16
like gamma contrast or even RGB curves that you can control for better result.
11:22
And now this looks so much better. Now the only thing of course is that you cannot just simply export that to Unreal
11:28
Engine or Unity. But that's not a problem. You can easily bake that into the new texture and that's done in few
11:34
clicks. But I also will show you how you can not only bake that in new texture but also bake these two objects in new
11:42
texture because again like why not them to use one material. They're like old boxes. So I joined the objects and
11:49
duplicated them. I'm going to call them high low but they are basically same poly count. Then on low basically
11:56
objects I going to bake on I removed all materials and created new one and call it box. Now one thing we need to do to
12:03
make this work is to reun objects or actually at least pack it to make sure
12:10
that the UV space they use is not overlapping. There's an amazing free add-on called UV packer and I just did
12:17
that in few clicks. Right. I select it all objects in edit mode. Click unwrap.
12:22
Click pack with the the margin. And that's it. Now this objects are one
12:28
object with new material and UV that doesn't overlap. Last thing we need to do is to create new texture again here.
12:35
Just create new image texture. Give it a name box color. We can connect it to a
12:40
shader. And let's do the baking. We're going to go to cycles engine bake option
12:45
here. Going to choose diffuse. We're going to uncheck direct and indirect lights. Select it to active. And here
12:52
usually we need to set this value for 001. Then we can enable cage. Those objects are identical. So we just need
13:00
one extra mill to do the coverage. And since we do selected to active, we're
13:05
going to click on object that we're baking from. Then baking on with shift.
13:10
Make sure that in target object the right node is selected and click bake.
13:15
That will be almost instant. And here is the result. Now we can hide that source
13:21
object. And here we go. It's now not only new color but also in one texture
13:28
atlas. Similar way you can bake five objects together like 10 objects together. Just make sure it's reasonable
13:35
and that all objects are not that blurry. Like I mean you decide like on texture size, on purpose how this
13:41
objects going to be used and so forth. And if you guys like my workflows and want seriously improve in making game
13:48
levels or characters, I have amazing news for you. Me and my team, we just
13:53
finished working on 3D AI course for game levels. And that's just mind-blowing. We're going to guide you
13:59
from very beginning how to work with the idea and how to get your game level
14:04
ready. We already have hundreds of happy students from character course and now it's time to build the worlds for these
14:11
characters. And to celebrate that for launch week, there will be special discount for anyone. All links will be
14:17
in the description. Another thing that usually pops is PBR. For example, I have this pen. And what I going to do, I'm
Setting Up PBR Materials
14:23
going to go and just create two textures right in shader. One for roughness and
14:28
another for metallic. And by default, those are black [music] maps. We're going to need to set them to non color
14:34
cuz we're going to work with properties. And of course, we're going to go to texture paint. Now here there is a fill
14:41
brush and we can sort of set the properties with the values like this that will also paint this information
14:48
into the texture and just like that I can create right material. The cool thing about creating maps is that you
14:53
can always switch to brush and for example make one area less reflective. Here's one example. I made it like
14:59
extremely metallic. I'm going to reduce the brush a little bit and now I going to paint with complete black on
15:06
roughness which will make it maximum reflective. Right? So I going to paint like that and it will become almost
15:12
mirrored. You can see it's extremely reflective. Or if I change it to white
15:18
then it will be absolutely non-reflective. Now let's talk about one more thing big assets. Big assets like
Creating Rocks and Tiled Textures
15:24
big surfaces that still need like detailed texture and usually there is tile texture used because generation is
15:32
limited. Or there's a second approach. We're going to build big objects from smaller jacks. That depends on multiple
15:39
factors. If you saw my previous video where I created souls like game level, I was using tile texture for big surfaces
15:46
also using with normals and stuff. Here I have a bit more difficult challenge because this is a big cave and if I just
15:52
create some surface and add that tile texture, it might lose some big bumps
15:58
and [music] so forth. So I decided to create it from smaller chunks of rock. So here's how I did it. Here are my rock
16:04
chunks. What I going to do in Blender? I'm going to first resize them. Then I'm
16:09
going to duplicate them and create low poly version. But I don't need any low
16:14
poly generator. I'm going to just do that with decimate. Here I'm going to choose extremely low value because I'm
16:21
going to need a lot of rocks to do that cave. And I can go as low as 0.1 and
16:26
even lower. Here you can see the final result. Again, I actually did that twice. So each of my rogue, like
16:32
basically two of them, only have around 1,000 polygons, right? I actually did
16:38
that from 1 million polygons. So that's significant. And you can see it just follows the shape. Of course, I cannot
16:44
use it right away. It will be just ugly shape. You can see how it looks. But what I can do is that I can bake the
16:51
normal map from my original high polar object. But before that, I decided to quickly do some manual UV because this
16:59
is not a difficult shape. So you can see I just set some seams, just some lines,
17:05
like some cuts. Again, like UV is basically imagine yourself as a tailor
17:10
and you just need to tell like how to cut the garment so we can easily paint it later. There are many benefits of
17:16
proper UV that allow you to fit objects better and work with textures in easier
17:22
way. Poor boss UV and baking. I have amazing free short video on my YouTube
17:27
channel. Take a look. So I did unwrapped it and you can see I just have few islands. I can preview if there is some
17:33
stretching and maybe add some more cuts. Now just create new material. Create new
17:38
map. We're going to call it normal map. And you can choose the resolution. I will actually choose 4K because again I
17:44
going to multiply this object quite a lot. And do the baking. Just go to cycles, choose normal map, select it to
17:51
active. almost the same settings. Maybe we can make the cage extrusion like lower because the shape it doesn't
17:57
follow like exactly and press bake. And here's what I got. Quite amazing normal
18:02
map. So I connected it to shader. Now look at this low poly. I think that's pretty pretty good. Now we're going to
18:08
use that normal map and I going to need to color and maybe roughness and metallic. To do so, we're going to
18:14
generate style texture with Gemini. So here's how I did like a very very simple short prompt and I got results something
18:21
like that also ask it to generate like normal map and roughness map but we already have normal map we can combine
18:27
them together or I going to just use roughness map best paid alternative will be patina one of the best AI model for
18:36
seamless textures original provider is fallai so you can take a look there it
18:41
is also available in some platforming tool great now I'm going to bring this color and roughness maps here and
18:47
connect it to shader. I was a bit unhappy about the roughness. So I connected it with gamma to adjust the
18:54
value a little bit. Yeah, I just wanted [music] something like this to not too reflective. Good, good, good. Now it
19:00
looks uh like a rock. Only issue is that the scale is wrong. So I'm going to click on this node with Ctrl T. That
19:07
will add this mapping so I can adjust the scale. If Ctrl T doesn't work, make sure that in Blender node wrangler addon
19:15
is activated. It's included in Blender but sometime is not activated. Here we can try different options instead of UV.
19:21
Sometimes like generated or object can work nicely. And yeah, the most
19:27
important thing is to adjust the scale. Yeah, I was trying like four or six and I think I'm going to stick with four. I
19:33
really like the result and I really like how it actually works together with my normal map. My rock is ready. The last
19:39
step is of course to bake this final transformation. Again size and color correction will be baked into texture
19:46
slot. New color texture, new roughness texture. The process is all the same. Just select different baked type. For
19:52
example, for color it's diffuse. When it comes to roughness, we change bake type
19:57
to roughness. And you can again bake much more like metallic etc. Now I can
20:02
delete all other nodes. Boom. And here's the final result. My building blocks are ready. I can then repeat same process
20:09
for the rest of rock objects like build big other objects. And here you can see my final list of assets. I call it a
Level Assembly in Blender: Pier and Optimization
20:16
starter pack. And these are not only AI generated objects. I already prepared them, processed them, adjusted where
20:23
needed, generated some materials etc etc. These objects are what player will see in the game. Let's move to the fun
20:30
part and it will be about assembling. First of all, don't forget to bring your reference image. Here in Blender there's
20:36
image and reference that will add any image inside in Blender and that image
20:41
is always visible regardless what shading mode is for other objects that will reduce amount of switching and now
20:48
we can actually assemble thing. First thing to do is to understand where you start. I always recommend to divide it
20:55
into simple chunks. For me first chunk was pierce and that was frankly like the
21:00
easiest chunk to start with. Later I going to build everything around. I will not start with the cave because cave is
21:07
big and I don't really know the exact size of a cave because it must nicely cover pierce. There must be some space
21:14
from pierce to the side like like you see on the reference. So instead I will start with the assets that is known in
21:21
size right like this wooden pierce part the ladders this hut and this area. And
21:28
for me, it's so much convenient to do this object placement rather than in our engine. I don't know, it's just not
21:34
convenient there. And one of the best advice I can give you here is to learn hotkeys how to transform objects in
21:40
Blender very quick. There is absolutely nothing crazy. But it will make this process for you so much more pleasant.
21:47
At this stage, 80 to 90% will be just moving things around. sometimes maybe
21:52
some simple procedures like like cut things, optimize if they go inside too much and so forth. So just 5 minutes
22:00
later I already have something nice coming up. And when you have this first step, it will be much easier to build on
22:06
top because that's not only first step that also a size reference for all the location. When you use big assets, one
22:13
thing you need to care is that part of the assets might be never visible to player. For example, I had this big
22:20
rocks and there is no point to actually keep this bottom part. So I use the
22:26
knife tool like it's very very easy. You just like draw the line just cuts the
22:31
whole bottom surface. And I going to use it like this because again like that will save polygons like a lot of
22:37
polygons and especially if you start like to work a lot with them. You can use knife or you can actually cut by
22:42
boolean. And this is really the concept you need to know about this 3D software and stuff. There's a big fear that you
22:48
need to learn so much about blender or any other software. But in reality, you
22:54
just need to know few right tools and that's it. Like with knife alone, you can do quite a lot. I still don't know
23:01
95% of what Blender offers and I'm not sure if I need to
23:23
And here we go. One hour later basically. Yeah, this like this whole location all you saw with the time lapse
23:29
was just 1 hour and I already have this I think most important chunk of this
23:35
location because rest will be built on top. And you might see I don't really spend much time like placing
23:41
accessories. I always keep accessories for the final mile. Start with big objects first. That's very important.
23:47
And again, anytime you miss some objects, [music] just go back and generate them. That's super easy and
23:53
fast. How cool is that? AI alone will not be able to do that. Great job. At
23:58
least not soon. Just think about how many decisions you make along this process. Like where to put that, how is
24:05
going to look better, like where not because you basically tell your story through this. And I truly believe this
24:10
is art. It's just the pen evolved. Instead of drawing with polygons, we now
24:16
draw with ready 3D models. Now let's approach the cake. So as I said, I decided that I going to build it from
Level Assembly in Blender: Cave and Details
24:22
big chunks. To be honest, that's not the fastest way of course, but I keep all
24:28
the details that matters to me. So from inside again like it will look like actual cave. So for you it will be quick
24:35
time lapse but in real time I actually spend around 25 minutes to build up the
24:42
complete cave and it looks something like this. Well not that much basically I'm pretty happy with the result. Again
24:48
super important when you do so much placing transforming objects around it's definitely better to do that with
24:54
hotkeys. Then one last mile about the K was to add this stallic tits I think
25:01
they called right and I did not generated them. I just cut one of the
25:06
rock, scaled it a little bit and started to placing. And the good thing about this approach when you reuse the assets
25:13
when it's possible is that again they all are already using like one same
25:19
texture like you're already optimizing. So this approach is good by many means. My cave is ready. Just for fun I added
25:27
some lights to show you like what is the current stage. Yeah, of course, uh, in Unreal Engine, you're going to look much
25:32
better. Now, it's time for final step here. I'm going to hide the cave. It's done, but I'm going to just hide it. I
25:38
also really recommend you to organize your workspace. Like your workspace here is like collections. So, again, that's
25:45
going to make your life much easier. Like starter pack like one collection like uh the pierce one collection, cave
25:52
one collection. Cave is like bunch of objects etc. Just put them in one collection so you can hide it by one
25:58
click later. Placing accessories is very simple. Nothing to comment here. Like just just enjoy the time-lapse. I was
26:04
putting these papers all around the coins, small objects, lights. Of course,
26:09
the lights actually lights was the most important thing because later in Unreal Engine, I going to light them up. And uh
26:18
there were a few things that I even had to circle back when I started to set it in Unreal Engine. You're going to see it
26:24
later. I'm going to add the chain, the hook, all that things. One interesting
26:29
case and advice that I want to give you is that sometimes generating objects with AI is not optimal by speed and by
26:37
quality. For example, I needed a rope to connect this hook and the boat with the
26:43
pierce. So instead of going and generating the rope alone, I just created the primitive curve. The curve
26:50
is very simple object in Blender. It's just like a line that you can control and like very very easy and you can add
26:57
some depth to it like this and that will be five times faster than doing that with AI. So here you can see I just
27:04
control the bizier curves and it forms the right rope like this. Any shape like
27:10
this you can convert to mesh when it's finalized because when you convert it to mesh like you cannot control it through
27:16
bizier curve when you can actually delete that bizier curve. Then I added some simple cuts to unwrap it like you
27:23
can see here right into some line. And of course generated some tile rope texture with Gemini. And here I go. Look
27:31
at this nice amazing rope. Of course you're going to learn that over time. But if you're willing to learn. So for
27:38
example, even when you have this amazing cloth with Blender setup, I actually have a lot of videos about it. Don't
27:44
only ask it to do some stuff but I really encourage you to try asking like what is the best easiest way or fastest
27:51
way like to approach this task like I need a rope. Sometimes it will be this sometimes you can do that with
27:57
primitives like in few clicks. Learning one small thing per day will take you very far. Our game level is finally
Unreal Engine Setup and Final Result
28:04
completely ready for game engine. So let's export it and assemble in Unreal Engine. Again, as I said, this approach
28:12
works with Unity and GDOT even basically with any other engine. There are some
28:17
engine specifics, but I'm not going to cover them here anyway. That's completely different thing. But let me
28:23
explain my approach briefly. First of all, we bring all objects to Unreal Engine. And I guess like the most
28:29
annoying for me right now is that I have to go through each uh material and
28:34
recreate the right PBR Unreal Engine material, right? Even though you prepare old maps etc nicely but they are not
28:41
really optimized. A good thing about is that uses the same textures etc. that's
28:46
totally fine. Some assets like water etc you don't really need to take care about
28:51
uh in Blender because there will be dynamic assets and for that I absolutely love Unreal Engine like grass for
28:57
example like water weather and weather in my case is probably the most
29:03
important thing. I really love two add-ons that I use all the time which call like ultra dynamic sky, ultra
29:10
dynamic weather. Again, all this beautiful images that you see from my videos, not only about nice 3D but also
29:17
how you sell it. That's something important I learned from game design. So sometimes I can spend one hour like two
29:23
hours like doing some different light options, placing some lights around, playing with weather, with the sky, etc.
29:31
And I mean, you actually do that like first because when you're going to place this point lights around again and they
29:37
it's all works together. And I absolutely love how this water with this
29:42
light from the cave came up eventually. I mean like that took a while but again like this not nothing crazy there like
29:48
overall I spent around 2 hours in Unreal Engine doing this main setup placing
29:54
lights around adding some VFXs etc. I also did some animations that boat on
30:02
the rope. So, it's moving a little bit and also for the boat that is on the water. So, it's sort of like again
30:09
floating a little bit. I remember a long time ago that adding all this, you know, animations and stuff is so difficult.
30:16
But again, like Unreal Engine is something crazy right now. Again, those things you can add like in 5 minutes
30:22
like physics, some animations through shaders. There's plenty of ways how you can do that and recently there was like
30:29
Unreal Engine 5.9 announced and they say there will be even more AI possibilities
30:35
there and there which bringing that native MCP and by the way if you haven't seen that I really recommend you to take
30:41
a look at my video about new Unreal Engine MCP and while I was talking that much look I already have this all set
30:50
just look how amazing it is I mean I'm super happy about myself especially
30:55
especially about how sun goes from this cage entrance. It's such a cozy nice
31:00
small location. That's exactly what I had in mind like when I was building the app and honestly there is nothing crazy
31:06
I did a bit of taste good idea right approach this right approach very important again AI is a great great tool
31:13
but you still need this tool to get something really great that was Steph definitely don't forget to hit that like
31:20
button guys this was a very big video and I see you in the next Hips.
