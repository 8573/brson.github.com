---
layout: post
title: The Minimally-nice Open Source Software Maintainer
tags: [rust]
---

Being involved in open source software is rewarding, yeah? You start
off contributing to your favorite project, and it feels so
heartwarming when that project's maintainers recognize your
effort. Then a few years later you somehow end up responsible for that
project, and maybe some satellite projects, and people are clamoring
for your attention, and your inbox is never empty, and it's exhausting
and terrifying, and the skills necessary to cope with all the
personalities involved are entirely different from the skills you used
to get your foot in the door in the first place.

I love creating cool things, and releasing cool things, and receiving
praise for cool things. To create ever cooler things though one needs
to multiply their manpower, get help from others - to _collaborate_.
Ugh. For me communicating with others is frightening, stressful,
unpleasant, demoralizing, depressing. As the maintainer of a number of
projects related to the [Rust programming language][r], I want to see
my software grow and thrive, so must continually redouble my efforts
to productively engage with their users and contributors.

Any day where I am actively maintaining my software I might respond to
dozens of messages online. It's so much effort. But amidst all that
work, it actually only takes a small amount of consistent effort to
nurture a coorperative environment, one that makes participants feel
appreciated, builds support from your userbase, encourages
contributions, and reinforces a positive culture. Still, even though
it's quite simple to treat others right, it's not simple to do it
consistently: it requires discipline to build good habits. For me it's
a struggle.

Here I'm going to describe a few guidelines on how to respond to
people on bug reports, pull requests, and other forums. I don't
consider myself to be good at this; I definitely don't follow my own
advice consistently. But what I've scribbled down here reflects my
basic gameplan for dealing with people, and having a clear gameplan
makes it easier to rip through your responses to both the pleasant and
the horrifying, quickly and correctly. My understanding of this
subject is always evolving, but this is what's near the top of my
mind as of mid-2017.

This simple advice might sound patronizing. And you might have
different opinions about what it means to be nice to people. That's
fine. Perhaps consider whether you are following your own gameplan
consistently, and how you might improve it.

This is divided into two sections:

- [A case study](#a-case-study). My lamentations at being a heartless
  jerkwad.
- [The techniques](#the-techniques). Common techniques for dealing
  with people, as applied to open source software.

If you just want a TL;DR for seven techniques of the minimally-nice
open source software maintainer, then [jump straight to the
summary](#summary).

<a name="a-case-study"></a>
# A case study

The impetus for writing this was [a comment I made][c1] on a recent
Rust RFC. As usual, this was one of many threads I responded to that
day. And as happens with some alarming frequency, I spent a large
portion of the night regretting some of the things I said, and
thinking about what I should have said differently. I'll reproduce it
here so you don't need to click the link:

> I like the direction of this RFC generally.

> `--explain` is a stable compiler interface. How can we change it? I
  agree that `--explain` is a sweet name for this functionality, but I
  think we need to use a different one.

> It's not clear to me what the fate of error codes is here. My
  impression is that you are proposing to remove them, but your images
  contain the current --explain E0002. Can you make this more clear,
  and if you are removing error codes can you remove them from the
  graphics?

> > "Famous programmers like John Carmack have praised the Elm error
    format."

> John Carmack's fame doesn't really have any bearing on the validity
  of the proposal.

> _Also, I don't think RFCs should be giving props to other
  contributors in the summary. When creating the RFC process we made
  an explicit decision not to include author information, to avoid
  making RFC authorship itself an incentive (I think). If authorship
  is something that should be included in RFCs then the process itself
  should be modified to include that metadata, including crediting the
  actual author, not just their collaborators. If giving credit in the
  RFC text is something we want to encourage, then I don't know that
  the summary is the place for it. The summary is for summarizing the
  content of the RFC._

I've emphasized the part that haunted me most.

I wrote this at the end of the day, in a hurry, between meetings. This
was a proposal that I had opinions about, and I wanted to make sure
they were heard. But it has to be done in the right way.

Really, this comment wasn't horrible. You've seen much worse I
hope. But it bothered me. A lot. I didn't follow my gameplan. I knew I
had made a mistake when the author of the RFC messaged me privately,
saying, more-or-less:

> jonathandturner: :( why don't you want to credit people for their
  work?

My comment on the thread sounded like I wanted to deny the
contributors credit for the RFC. Is that really what I wanted? Well,
honestly I am an overflowing flagon of resentment and spite, so
perhaps this comment in the moment was a true reflection of my
blackened heart, but after some back and forth with @jonathandturner,
and some further reflection, I understood this was a dumb position to
hold - being extremely generous with credit is one of the easiest and
most powerful techniques for building community. Outright suggesting
we deny credit looks petty and hostile.

Let me go through my comment line by line and excoriate it.

> I like the direction of this RFC generally.

I'm relieved that I started the comment this way, considering how
negative the comment ended. This isn't a fantastic opener, but at
least it's positive. Showing others appreciation is one of the simplest
techniques for dealing with people. What I wrote here is just about
the minimum appreciation I can express. It's saying I like what they
are thinking. It's obviously setting the stage for less positive
feedback later, but we don't need to worry too much about that - even
the slightest effort at showing appreciation tends to help soften
interactions, though there is a risk of being seen as patronizing,
particularly if all your praise is as curt as this.

So this could have been better in an obvious way, just by expanding on
what I liked about it. There were a lot of great facets to this RFC:
the beauty and clarity of the proposed error messages; showing images
of the proposed errors, etc. It's a good RFC - I could dig out lots of
little things to say positively about it. But doing so takes time and
effort. I was in a hurry here to say the things I wanted to say, and
didn't take the time, but perhaps I should have. The more negative
your main points are, the more worthwhile it is to soften them with
positivity. And it's prudent to show that positivity sometimes to
avoid being a complete jerk.

Another simple thing I could have done is thanked him for his
work. When you work hard on something and then finally unveil it, it's
super satisfying when somebody thanks you, recognizing that work. We
all long to feel appreciated. I might instead have opened with

> Thanks @jonathandturner! I'm glad to see some movement in this
  area. This is a super important proposal, the design looks well
  thought out, and I love how well composed it is. It's obvious you've
  put a lot of effort into it.

> I like the direction of this RFC generally. The error messages are a
  huge improvement over what we have today. The way you are using
  colors to emphasize the different focal points of the errors makes
  things a lot more readable. And good idea including the images of
  your proposed messages in the RFC - that makes it simple to
  evaluate.

OK, that's really loading up the praise. And it's all true. The above
took me a few minutes to come up with, which is a fair bit of work
just to grease the wheels. One might do more or less depending on the
situation. Now that we've pumped him up we're ready to crush his hopes -
er, offer gentle, constructive criticism.

So back in reality, I didn't actually write all that - I wrote the
impulsive thing, then tossed and turned all night regretting it. To
make up for it the next day I posted [this followup][c2], reproduced
here:

> @jonathandturner my comments could have been more constructive. Let
  me respond to myself.

> > > "Famous programmers like John Carmack have praised the Elm error
      format."

> > John Carmack's fame doesn't really have any bearing on the
    validity of the proposal.

> Maybe just change 'fame' to something more relevant, like
  'well-respected', something that better indicates why his opinion is
  important.

> > Also, I don't think RFCs should be giving props to other
    contributors in the summary. When creating the RFC process we made
    an explicit decision not to include author information, to avoid
    making RFC authorship itself an incentive (I think). If authorship
    is something that should be included in RFCs then the process
    itself should be modified to include that metadata, including
    crediting the actual author, not just their collaborators. If
    giving credit in the RFC text is something we want to encourage,
    then I don't know that the summary is the place for it. The
    summary is for summarizing the content of the RFC.

> I phrased this too strongly. I just had a sudden observation that
  we've developed ad-hoc ways to credit people that doesn't fit into
  the process as implemented. I should have phrased this more like
  'maybe we should reconsider how to give credit in RFCs'. RFC process
  is organic so it may be perfectly fine to do it like this (author
  credit in the commit log, additional credits in the summary), but it
  is awkward. And I do believe we made an intentional decision not to
  credit people, and if that is changing it is important to
  acknowledge it.

That was ... ok, I'm still not particularly happy with it. It still
appears a bit defensive of my dumb position. I wish I could do it
again. I'll never be happy. I'll never, ever be happy.

But the point is that it's best to admit your mistakes, to yourself
and others: Dale Carnegie recommends that "if you're wrong, admit it
quickly and emphatically". People love to be right, so if you can
admit that you are wrong and they are right, that can inspire great
cooperation. And it usually doesn't require any sacrifice at all to
admit you are wrong besides getting over your own pride.

<a name="the-techniques"></a>
# The techniques

So this relatively minor episode caused me to reevaluate how I
communicate online. It's not like I don't know how to be nice. I
believe that I do, but sometimes I forget momentarily. So here, to
reinforce my own good behavior, and hopefully for your benefit, I've
traced through my basic gameplan for responding to people online.
When I stick to this plan things mostly go well, the people I
encounter feel good about Rust and their association with it, and I
feel relatively ok-ish about myself.

The techniques here apply to any open source venues, like pull
requests, issue trackers, mailing lists and forums.

<a name="respond-quickly"></a>
## Respond quickly

Immediately after users and contributors reach out to you is when they
are most motivated to help you. Simply getting a quick response can
make a frustrated user's day. As a maintainer I've frequently seen
expectant users express their appreciation: 'thanks for the quick
response!'. We know that other people's time is valuable because our
own time is valuable. By responding to an inquiry quickly we
demonstrate that we respect the time they put into e.g. filing a bug
report, and that we are sacrificing our time to help them. Even if I
can't think about a particular issue right now, and particularly if I
_know_ I'm not going to get to it any time soon, I will sometimes post
a quick acknowledgement and validation of their concerns, like "thanks
for the report. This does look troubling. I'm afraid I won't be able
to look into this soon, but help is appreciated", etc.

The longer you wait to respond to a contributor the less likely they
are to stay engaged: only the most hearty contributors will return to
the table after being ignored for a year. Sadly, it's all too common
that I come across an issue where the most recent comment is from
someone seeking advice, long, long ago. Those contributors are lost
forever, and their potential contributions with them.

For me this is one of the hardest habits to maintain. The neverending
crush of issues and threads in Rust is entirely overwhelming. I'd much
rather I didn't have to face other people's problems constantly - I
have so many of my own. It's impossible to follow everything going on
in Rust, so in practice I tend to restrict the threads I follow to
specific areas, and to those people who are pinging me directly. There
are long stretches where I just can't face the endless tide of other
people needing assistence, where I will just willfully ignore my
inbox. I don't recommend that. Better to be responsive.

How quick is quick enough? 3 days. How scientific is this number? It's
not. You should respond as quick as you can, but reasonable people
will give you a weekend without getting bent about it.

<a name="give-thanks"></a>
## Give thanks

People like to feel appreciated. It's a universal desire. And
appreciation is something it costs us little to give, to spread about
like parade candy. If you put just a moment's thought to it, I know
you can see something good in every person and every situation.

The mere act of submitting a patch is awe-inspiring: another person
cares enough about our project that they took the time to understand
how it works, fix our problem, package it up, and submit their work
for public criticism. That's amazing. Do you remember the first patch
you ever submitted upstream? I bet you were apprehensive. It's a
crucial moment that can determine the future relationship between the
contributor and the project.

So the first thing to do before mounting a response is to dig deep
into your reserves of universal love, kindness, and compassion, and
seek something to be thankful for. The more specific you can be the
more it shows you care. Did they provide a reproducible test case in
the issue report? Damn, that took some effort! Did they write tests
for their patch?  Noway! Usually I have to ask for those! If you keep
thinking about it you'll discover there's a great deal to say thanks
for: "Thanks @AHumanWithFeelings! I've been wanting to fix this
issue for so long. I'm glad somebody finally stepped up to write a
patch. This looks lovely!"

Of course, not every encounter demands laying it on thick, but do say
"thanks". Even trivial patches that can merge without any feedback
deserve some comment: just hit the merge button and and write,
"thanks!", and they'll feel good about the small part they played in
your project's ongoing success.

<a name="pay-a-compliment"></a>
## Pay a compliment

One of the primary duties of a software maintainer is to review
others' work. Every day, burning down the endless patch queue. And the
bigger the project the more gruelling the work. Review is where
everything comes together; it is the make-or-break point for
contributors, their work, and their motivation to keep coming back.

Under the exhausting crush of review responsibilities it's easy to get
tunnel vision; to bee-line for the shortest route to the end, zeroing
in on the problems to be fixed, and moving on to the next patch.

When you do this though you risk discouraging your contributor. The
more work a patch needs the more the critiques pile up, and it can
easily, and unintentionally, result in an avalanche of
negativity. This is particularly likely to affect new contributors,
who are least likely to understand project norms, and most likely to
need guidance.

A well-known technique to soften the weight of criticism is to pair it
with praise. You've probably heard of the "compliment sandwich":
surrounding the criticism - the meat of your response - with a soft
and squishy bun of praise. The compliment sandwich is considered so
delectable because it is simple and effective. Before you launch into
_what you really want to say_, try to look for something positive to
point out first.

When I review a patch I usually do it in two passes: first I skim
through it with an open mind, with no preconceptions of what I expect
to see. I'm trying to get in their head and see the solution from
their point of view; and in particular trying to find things to like
about their solution. Does the patch display good intuition even while
getting the details wrong? That's a good starting point. Did they do
something clever that you hadn't considered? Does their work
demonstrate they've read the project's contribution guidelines in a
way most contributors don't? You probably have a host of things you
look for to indicate quality, as specific to your project. Make note
of them as you read the patch, _and say them first thing in your
response_. Myself, I always appreciate when a contributor writes _any
tests at all_, and I adore contributors who write excellent tests. And
I say so. To take this technique to the next level, be on the lookout
for indicators of the contributor's own values, and compliment them on
things they are likely to take special pride in.

By reading the whole text once I additionally reduce the chance of
coming to mistaken conclusions, or leaving comments based on
incomplete information. Often I've not considered a work as a whole
and left a comment, then moments later realized that comment was
mistaken and had to correct myself. Likewise, I find it frustrating
when reading inline comments about my own work based on incorrect
assumptions, and which I felt I had made clear if the respondant had
only read further.

So after I've done the first pass in a spirit of expansive generosity,
and begun composing my review with praise, then I go back for the
second pass and do the detailed review. Even here though I try to note
positive things as well as things that need to be changed, etc.

I've focused on reviews here, but the same applies to all
correspondance. Bug report includes a reduced test case?
Awesome. Forum post is well thought out and polite? Halleluja. Always
be looking out for nice things to say about your peers and their work.

<a name="say-yes"></a>
## Say "yes"

In the midst of an internet argument it's easy to lose sight of the
humanity of the individual on the other side of the computer
monitor. Your pulse quickens, your temperature rises, mind races. You
know you are right, technically, morally. Whatever, you are right;
they are wrong. Wrong, wrong, wrong, and you are going to prove it
right now.

But before you fly off the chain, prove your undeniable superiority,
and prove that _they are wrong_, let me suggest instead that you do
something better, that you do the opposite: that you _prove they are
right_.

Imagine the most exciting brainstorming session you ever had: you spit
out a brilliant idea - your partner loves it! They respond
enthusiastically by building on your idea. The conversation spirals
ever upward in joyous rapture. It's an amazing feeling, being on the
same wavelength. By the end up the night you feel thrilled and
intoxicated. That's the power of positivity.

It's so rare. When it happens we want to capture that moment and save
its precious essense forever. That's the kind of magic you want your
contributors to feel every time they file an issue.

The opposite though is far more common, and it's the death of useful
discourse: "you're wrong", "that's a bad idea", "I call bs", "meh",
"false", etc. They all amount to a big fat "no", and they all make the
recipient feel disrespected and generate ill will. Bad vibes. This is
the worst way to open a productive conversation, and people do it all
the time. It's shocking how tactless smart people can be. Such direct
negativity erects a brick wall fortified with turrets and kettles of
boiling oil in the middle of a conversation.

"No" is a cardinal sin of pursuasive argumentation. Don't do
it. Don't do it. Don't do it. No, no, no!

Instead, say "yes" as fast as you can, and in every way you
can. Literally just say "yes" first thing, then figure out what useful
affirmation you can follow with to support that "yes". If "yes" is too
on-the-nose for your taste then there are a billion ways to
paraphrase. "Yeah" is a great casual option, and my favorite. Follow
that with a comma, "yeah, it's true that ...", but there are so many
other more subtle ways to drop a huge positivity bomb at the outset of
your response: "totally", "you're right about ...", "indeed!". If you
put your mind to it you can spend a whole paragraph just saying "yes".

In the end, even if the solution is much different than their original
proposal, by chaining your good ideas to their good ideas, they will
feel successful. Per master thinker Blaise Pascal, "people are
generally better persuaded by the reasons which they have themselves
discovered than by those which have come into the mind of others."

Affirmation: it's the secret weapon against belligerent jerkwads.

<a name="be-clear-about-what-you-expect"></a>
## Be clear about what you expect

For contributors to stay engaged they need to know what's next, what
is expected of them. This applies to every level of the project, from
bug reports to pull requests. If you want something, say so directly!
And if you don't want something, suggest concrete and viable
alternatives. For the most part, if you are in a position of
authority, contributors are _desperate_ for you to give them
direction. Leaving your desires ambiguous is one of the easiest ways
to destroy contributors' motivation and lose their manpower.

This applies especially in two places: on the bug tracker, and during
reviews. In both cases there is frequently a critical moment when you
have the opportunity to provide clear direction, and though it
requires some effort, failing to do so leaves a vacuum, and thus
leaves potential precious manpower on the table.

Your issue tracker, if it's like Rust's, is filled with bugs and
feature requests that you would love to fulfill; but you will never,
ever get to them yourself, not even if you live forever. These
bugs frequently persist in a state of unknowning, where the solution
is unclear, for weeks, months, years, accumulating debate and
discussion about how to move forward. But eventually something clicks
into place, and an acceptable solution becomes known to you. For
simple bugs this moment can be immediately when it is filed; for more
nuanced bugs it can take a long time. But when it happens, you have
the opportunity to clear the way for contributors.

On any bug where there is an acceptable solution, make it crystal
clear what that solution is, and that _help is wanted_. Contributors
are sometimes just waiting for a signal indicating how they can
help. The more detail you can provide the better. Bugs with clear
direction have 100% better chance of drawing contributions than those
without. The larger your project, and the larger your contributor
base, the more important it is that you consistently provide
direction, and that contributors have a way to find the bugs that have
reached this inflection point.

<a name="admit-your-mistakes"></a>
## Admit your mistakes

Like variable bindings in a great many programming languages, our
reality is supremely mutable. Conditions change, facts change, and so
does our perception and understanding. Being wedded to past
understanding and past resolutions is dogma. On the other hand,
confronting change honestly and efficiently is a common trait of
successful individuals and organizations. The agility to let old
opinions go and steer a new course helps organizations stay relevant
in the face of shifting fortunes, and helps us navigate difficult
social situations in our daily lives.

Differences of opinion are the root of many arguments. People make up
their minds, assert themselves, refuse to listen to counterpoints,
become angry, develop personal animosity toward those that don't
agree, and the conversation either reaches an ugly standstill, or
devolves into a passionate feud. It's a common failure mode, and we
want to prevent it from happening as early as we can.

Just like we want to say "yes", and acknowledge others' great ideas,
it's beneficial to look for situations where we can let go of our own
ideas, our own dogma. It's a hard thing to do: it's so tempting to
stick to what is comfortable; to force those difficult decisions that
have already been decided to stay in the past; to never let go of our
pride and admit we were wrong, or made mistakes.

But it gets easier with practice, and you might even come to find that
admitting your mistakes brings relief - it feels liberating to let
things go, to get that weight off your mind.

I find that there are very few designs and opinions that, when I look
closely, I am deeply wedded to, and most often when somebody is angry
at something I have done or some decision I have made, it is trivially
true that I've made a mistake. Sometimes these are technical mistakes,
and I can let them go by saying "yes, I see what you mean now. That
was the wrong call. Are you interested in submitting a patch to fix
it?". Sometimes it's more of a social or political mistake, that I
haven't expressed my motivations or intentions clearly and the other
person is surprised and disappointed that some outcome is not what
they expected. In these situations I try to acknowledge that the
result has the downsides they've identified, and apologize that it
doesn't suit them, and move on. Note though that it's best to avoid
the sorts of backhanded non-apologies we often see from politicians
(e.g. "I'm sorry you are angry"). Everybody sees through bullshit, and
it's more useful to focus on your own thoughts and feelings instead of
mindreading others'.

<a name="be-effusive"></a>
## Be effusive

This is another trick that is super-effective! A unique technique of
the internet age, I've only begun to acknowledge its power recently.

Don't hesitate to go overboard with superlatives and punctuation:
exclamation marks where they shouldn't be, over-the-top adjectives,
cute emoticon and emoji. I know that it took me a long time to come
around to this point of view. It's just bad writing to throw in
exclamation marks and superflous words, right? And emoji aren't even
words...

"Oh, wow, thank you so much! 💖"

Truth is that on the internet this is not bad writing, at least for
one-on-one communication. It is effective writing. It's well
understood that conveying tone on the internet is _hard_:

"Thanks."

What does that period mean? It looks so gruff. Are they pissed at me?!
Are they having a bad day? On the internet the simple period can
appear sarcastic, or angry. It's so neutral that people will project
whatever emotions they want on it. One must go out of their way to not
only get their meaning across but also the tone - and for our purposes
the tone we want is almost always one of abundant positivity and
enthusiasm.

To help you kickstart this habit, here's a list of some of my
favorite superlatives, emoticon, and emoji, when applied to
technical communication in open source software communities:

- "!" (exclamation mark)
- "super-"
- "totally"
- "amazing"
- "awesome"
- "really"
- <3 (heart)
- <3 <3 <3 (triple-heart!)
- :-D (big-ol' grin)
- 😁 (grinning face with smiling eyes)
- 😍 (smilling face with heart-shaped eyes)
- 💖 (sparkling heart)

These are just the ones in my own toolbag. There are so many others,
and there's lots of room for creative expression here. The younger you
are the more of these weapons you probably have in your arsenal, what
with all the texting and instagramming and tweeting. Deploy them
without hesitation.

There are limits to good taste here, but you probably have to decide
them for yourself. Personally, I never use more than one exclamation
point; two exclamation points is the epitome of tackiness 😜. And as a
child of the 90's I'm consistently tempted to sneak in a few
"radical"s and "bodacious"es, to embody my life-long wish to become a
Ninja Turtle, but sadly those adjectives seem to be out of style for
the present moment. The time will come though.

Just as a big smile can brighten someone's day in the physical world,
a little bit of 😍 goes a long way in the virtual world.

<a name="summary"></a>
# Summary

So that's all you need to make everybody happy, and make everybody
love you! Now you know the secret and you will never fail again.

Ha, ha, no. No, not really. Not everything goes smoothly just by being
nice. Some people are deeply broken. So many messed up people (maybe
I'm one of them - maybe you are too). Typical social wheel-greasing
doesn't always work with them; they are hell-bent on sowing chaos,
even if they don't know it. The guidelines here are still applicable
to these cases, because at least other, more reasonable, people will
see that you are doing your best, but truly dealing with them
effectively is a complex and uncertain matter. For another day.

Some of what I've said here may have sounded sarcastic, I know. That's
me. I'm a deeply cynical individual, but I'm working on it. Effective
communication though needs to be genuine, empathetic, and respectful.
Everybody sees right through bullshit. Work on your empathy, work on
being genuinely nice, but until then, fake it 'till you make it. If I
practice good communication habits consistently, presumably at some
point I will become a good person. That's how it works, right? I so
want to be a good person.

In summary, do these things if you want to _appear to be_ nice, and
also if you want to _actually be_ an effective open source software
maintainer:

- [Respond quickly](#respond-quickly)
- [Give thanks](#give-thanks)
- [Pay a compliment](#pay-a-compliment)
- [Say "yes"](#say-yes)
- [Be clear about what you expect](#be-clear-about-what-you-expect)
- [Admit your mistakes](#admit-your-mistakes)
- [Be effusive](#be-effusive)

By consistently exhibiting a few simple behaviors, one can at least
look like a kind and decent person. Maybe someday we all actually will
be.

_With respects to Dale Carnegie's [How to Win Friends and Influence
People][hw]. Read that._

[c1]: https://github.com/rust-lang/rfcs/pull/1644#issuecomment-224752975
[c2]: https://github.com/rust-lang/rfcs/pull/1644#issuecomment-224968147
[r]: https://www.rust-lang.org
[hw]: https://en.wikipedia.org/wiki/How_to_Win_Friends_and_Influence_People
