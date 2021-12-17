---
layout: post
title: How to detect humor and sarcasm in texts
permalink: /detecting-humor-and-sarcasm-in-text/
published: true
date_readable:               Dec 17, 2021
last_modified_at_readable:   Dec 17, 2021
---

_I received an email asking me how I would go about the dectection of sarcasm and humor in texts. A lot of papers on the subject have appeared but I didn't review them. I'd be interested to see what approaches are explored to date. The following is how I would approach the task:_

Sarcasm and humor are, in my opinion, cases that are very difficult to approach by machine learning. Indeed, a sarcastic or humorous connotation is revealed by very subtle clues, which would be very difficult to pick up by a model.

On the other hand, these very subtle clues are detectable if we examine carefully:

1. the different semantic aspects of the text (punctuation, vocabulary, grammatical structure ...)
2. the context: what comes before the text under examination, what comes after it, or even the speaker's profile (I expect the Twitter account of the United Nations to be less susceptible to sarcasm than an account coming from entertainment).

On the semantic aspects: I am a priori very confident of the fact that many sarcastic or humorous sentences leave semantic traces of their connotation - it is only very rarely 100% dependent on the context. Indeed, it is the subjective experience I have of it when I read sarcastic tweets. By re-reading them carefully, we can distinguish objectivable characteristics:

- sentence length (strongly positive sentences which are really terse can be a hint of sarcasm.)
- use of punctuation ("..." can be a hint of sarcasm)
- some vocabulary markers ("really" is a reinforcer, but "reaaaally" can be a hint of sarcasm).

So my approach would be labor intensive: read a lot of sarcastic-type sentences (difficulty: where to find them easily?), and reflect on each of them. What aspects of the sentence contribute to my subjective opinion that the author is being sarcastic? And then I'd try to codify those semantic traits as I did for [Umigon](https://nocodefunctions.com/umigon/sentiment_analysis_tool.html): creating lexicons and their heuristics + sentence-level heuristics.

I understand that one can be uncertain about the effectiveness of this approach: is it really possible to arrive at a list of semantic markers of something as subtle as sarcasm? My response is to turn the table on this argument. When or if sarcasm is impossible to pinpoint semantically, then a computational approach cannot get a grasp on it... __but neither can humans__.

To put it differently: when sarcasm is entirely context dependent (no semantic clue available), then machines and humans alike tend to be unsure about the sarcastic character of the utterance. This shows that the computational approach has not hit a limit, but instead that the person who made the sarcastic comment used to few markers to make its intentions (sarcasm or not?) entirely known.

An excellent example of this is an exchange betwenn Elon Musk and an unofficial account sharing news about [Rocket Lab](https://www.rocketlabusa.com/) on Twitter, dating from Oct 1, 2021. The account "Everything Rocket Lab" tweeted:

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">A small Neutron update before the official big one:<br><br>- Rocket Lab is still in the final downselect between the ultimate launch site according to Peter Beck.<br>- Neutron has become a bigger rocket! The rocket is now 46 meters high with a 5-meter diameter fairing.<br><br>📸: Rocket Lab <a href="https://t.co/S51bx9x4J4">pic.twitter.com/S51bx9x4J4</a></p>&mdash; Everything Rocket Lab (@RocketLab360) <a href="https://twitter.com/RocketLab360/status/1443933374813442051?ref_src=twsrc%5Etfw">October 1, 2021</a></blockquote>
<br/>
<br/>
To which Elon Musk replied:
<br/>
<br/>

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Will be Falcon 9 size sooner or later</p>&mdash; Elon Musk (@elonmusk) <a href="https://twitter.com/elonmusk/status/1444135225538265090?ref_src=twsrc%5Etfw">October 2, 2021</a></blockquote> 

In Elon Musk's response, there is no clear semantic hint indicating sarcasm (I guess the "sooner or later" + terse comment convey it, but this is not deterministic). If there is sarcasm, it is all context dependent, which made it hard for the observers of the exchange to be sure.

So, sarcasm or not? (I personally think this is sarcasm but could be wrong). Here, a computational approach wouldn't detect sarcasm, but neither would humans with any degree of certainty, because the context is pretty specialized (difference in development between SpaceX and Rocket Lab). So in terms of accuracy, the detection of sarcasm has a bar which is the level which humans are capable of detecting - and this is lower than in other NLP tasks (sentiment analysis, emotion detection, etc).

Still, how could the context be appraised in a computational manner? We would have to develop a tool which would be "platform specific" I think. Typically, a platform that allows reactions in the form of emojis would help, as one could rely on commenter's reactions such as "😆" or "😬" or "🤣" to signal that the content may be humorous or sarcastic. Apart from this, we could fancy more complex approaches (characterizing the profile of the locutor as "prone to sarcasm or not", but that would be a refinement, not a first step in my opinion).

So that would be my starting point! I'd be happy to exchange with researchers and students interested in the subject. If you are interested in my projects in text mining and graph minin, have a look at [Nocodefunctions](https://nocodefunctions.com/), a free web application that makes it easy to test and use the tools I have developed in the past years.