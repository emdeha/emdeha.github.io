---
layout: post
title:  "Space Apps"
date:   2014-04-17
---

<p>Collaboration my ass! You know, people try to do something. They strive to
collaborate in the creation of something beautiful, uniting and valuable. But
what happens when they try to do that? Well, if they're not careful, shitty
organization comes which ruins everything. Unknown figures which just want to
be approved of something, try to put their interests across the path of
innovation and friendship. That's sad and sheepish. But that's our world, you
know.</p>

<p>Anyway, the hackaton was exciting. I'm glad about the people I met and the
experiences I had with them. I'm glad that we managed to design and implement
something valuable, complex and astonishing. We did that in about thirty hours
with no loss of enthusiasm. All of us learned something new, all of us got
their minds and views extended by the technologies we had to deal with.</p>

<p>Maybe a tale of what happened would be boring. I'd just try to tell it in an
interesting way....</p>

<p>Well, I thought why not start with a story about some mythical creatures on
their path to happiness. Yeah, that'd be interesting. But I doubt it. It's so
distant from the things I'm going to write about. So, let's start simple.</p>

<p>I almost didn't get up on time. I was in kind of dreaming/waking up state,
when a staggering thought came through my bewildered mind. "Why was it so
bright in that room of mine? Well, maybe my alarm would soon go off...
Dunno." The next thing I'm doing, is I get up and pick up my phone. It was
7:12. Last weekend I had turned off my alarm. So I get up, put my clothes on
on and hurry to the bus station. I arrived earlier...</p>

<p>I waited in the somehow cold morning till it was time to get in. Momchi called
around 8:30 and we both got in. The Technical university's staff had done a
great job at renovating the place - it was all shiny and new. It's sad that
they teach such old stuff there... Anyway, at around 10:00 began the opening.
Some suit-guy was talking stuff he had crammed up not knowing what was it
about. I got over that. After him some old professors and uninteresting,
unexcited people came. They talked about bulshitbulshitbulshit. I started to
get little annoyed. You know, I think such things are no place for someone who
isn't innovative and motivated, for someone old. I think that the youth should
be in charge of such events. Of course, if there is an elder who is still
young at hearth, I have nothing against him or her to participate.</p>

<p>Well, the boring opening finished and we started with our challenges. We met a
guy who didn't have a team. He was an embedded developer and had an Arduino. I
and Momchi wanted to try something new, so we got him in our team. There was also
a really great guy which we met on the last year's Space Apps Challenge -
Tsvyatko. He decided to join us and before we knew it, we had four bright
minds who wanted to change the world.</p>

<p>We chose to make a satellite piloting simulation. We would render the earth
with its surrounding satellites and give the player the opportunity to cycle
through them and explore the universe around him. The first six hours were
procrastination on my side. I was still bewildered by the size of our task. I
had to get data, to chew it and to spit it in the form of a universe. Damn, I
thought, I don't know where to begin from...</p>

<p>Of course, you always don't know where to begin from. You're always scared of
the great things you'll have to do. Yeah, they're trivial, but you don't wanna
do them. You wanna sit in your comfort zone and not make mistakes. You don't
want to create... You want to destroy and observe.</p>

<p>By the evening, I managed to render the earth with a simple satellite.
Tsvyatko and Momchi set up a server which would give NORAD's two-line
formatted data into a human-readable JSON. Rosko, the hardware guy, had
managed to make the Arduino light some bars. Not much but we were all proud of
what we did.</p>

<p>The precious-looking technical university was closing at 22:00. Great! We
would make a hackaton with a rest. The good thing was, there is initLab where
we stayed and coded during the night. If we didn't do that, we wouldn't have
achieved a thing.</p>

<p>And the night was our most productive part of the day. I tried to set up the
server and get the JSON from it, in order to render the satellites at their
real positions. I got tired, mad and grumpy, left everything and went to nap
for an hour. I got up even grumpier. I made a strong coffee, mumbled a few
words about that I'll start doing exciting things in a moment and really
started doing them. Half an hour after I got up, I felt absolutely rested,
motivated and productive. By eight in the morning, we had satellites and Leap
Motion controllable camera. We also had gestures which enabled us to switch
between the sats with a simple swipe. It was great!  </p>

<p>At around 9:30 we were at the university. We still had lot to do! Rosko and
Momchi prepared the rest of the Arduino control board. I and Tsvyatko tinkered
with the server in order to make it give the right data. In the end, we
noticed that the time intervals we were giving to the NORAD converting lib
were too small for it to give us some delta. We configured them and we had a
real moving and buzzing horde of satellites! It was exciting and super cool.
We were all reallyreally happy. After that, I tried to clear the scene of the
spawning satellites.</p>

<p>You see, every thirty seconds or so, the simulation wanted new data from the
server. When it got the new data, it created new satellites. Now I realize
how dumb I was... I could've just updated the positions of the spawned
entities. Instead, I created and deleted them... Well, fatigue does strange
things to your mind. By the time I managed to properly do this, we had only an
hour left till the presentations started.</p>

<p>I still had to send data through the serial port to the Arduino module.
Meanwhile, Rosko was debugging an electricity leak in it. The presentations
began. I managed to send data, but it was displayed wrong. By the time it was
our turn, I almost debugged the problem. We had to go.</p>

<p>I plugged in the Leap Motion nervously and it started searching for drivers.
Damn! What could be wrong now?! We were walking to the stage, I was with my
laptop on my hands, debugging shit and we were going to present that bogus
stuff in a couple of seconds. Anyway, by some strange, existential ways,
everything got up and running. The good guys at the event didn't had an HDMI
cable. We couldn't put a projector on my laptop. Cool...</p>

<p>We began. One of the jury asked will we put this on the big screen. I had
really hard time keeping my anger. I told him as calmly as I could, that if
they had an HDMI cable we would've done this. Tsvyatko saved me from further
explanations and started the presentation. Momchi did a great job at it.
Despite not having a projector set up and doing everything on the small
screens of our laptops, we put the jury in awe. They were astonished, at least
the young ones. The questions they asked were somehow good. Sadly, I don't
remember much. When I get excited, I tend to forget thingsthingsthings. </p>

<p>We sat and waited. We weren't the winners. I don't know, I don't wanna say
anything about the votes. Maybe I'm biased, but I think the winners weren't
the right people. I just don't know. I was, erm, disgusted by people. Yeah,
although being fun and exciting, this competition killed a tinytinytiny part
of the place in my soul where I still believe people are good. It killed some
naiveness. That's sad. I want to be naive! It's fun, it's exciting and
interesting to think that all people are good. Damn! Yes they are!</p>
