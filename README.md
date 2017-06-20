# Bot Commons

The goal of this project is to define some industry common practices to publish metadata for bots.

The lack of common practices to complement bot software make it difficult to impossible to implement automated tooling for bots (such as discovery, versions transitioning, bot status) as well as inform end-users efficiently (such as bot commands, usage policy, feedback submission, point of contact for support).


## Terminoloy

### Bot

We define hereafter a bot as a piece of software that human interact with through textual messages or voice;

Typically a bot will push its interactions via a physical device used by humans whether a Phone (standard voice calls and SMS), a smartphone or laptop (via rich chatting systems, with Audio & Video capabilities) or any other material equiped with a piece of software (think of an ear device).


### Media & Channels

The media used by the bot to communicate with an end-user.

A bot could support several media so that it can be exploited from several chat, audio or Video platforms.

For each media, the bot can interact through one or several channels qualitied as Media Channels. Whereas most devices allow only simultaneous video or audio channel, messaging platforms let users and bots echange on several channels simultaneously (and generally asynchronously).


## Principles

This effort is lead from the bottom up, meaning that the set of metadata proposed by botcommons will be incrementally grown from real-world needs, documented via use cases.

We will thrive to keep backward compatibility but won't make it a first priority as the overgaol is to make botcommons cover most commons industry scenarios incrementally. 

From other bottom up specifications experience, we can evision that we'll come up with a first version from most common requirements in pretty short term, and then work on a v2 incorporating more advanced requirements on the longer term.


## Arbitrations

We value community feedbacks and will leverage github issue for the purpose of receiving feedbacks.


## Contents

The botcommons specifications is composed of this background document, the metadata description, as well as a set of use cases covered totally or patially by the specifications.


## History

This initiative started from the [node-sparkbot]() framework where we felt like we need to expose a enriched healthcheck which could serve several needs: know the bot is running ok, reachable from the internet, check the identity it is running against, the notifications he can listen to. 

Over time, we realized that adding extra metadata would certainly benefit the bot industry to get more mature by sharing common practices, and eventually come up with universal tooling.

We shared these thoughts at CodeMotion Milan, Rome, Amsterdam, then  and DevNetCreate, and finally saw enough interest from various bot community members to start writing down a draft for a first set of metadata.

The Swagger and APICommons specifications are seen by the authors as inspiring examples of bottom up specifications, with a start small / thinkg big kind of attitude.
