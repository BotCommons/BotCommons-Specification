# BotCommons: metadata for bots

The lack of common industry practices makes it difficult to impossible to implement automated tooling for bots (such as discovery, versions transitioning, bot status) as well as inform end-users efficiently (such as bot commands, usage policy, feedback submission, point of contact for support).

The goal of this project is to fill these [gaps in User Experience](UseCases.md) through industry [common practices and standardized metadata](BotCommons.md).


## Principles

This effort is lead from the bottom up: the proposed practices and metadata are incrementally grown from real-world end-users concerns documented via use cases.

We will thrive to keep backward compatibility but won't make it a first priority as the overgoal is to make botcommons cover most commons industry scenarios. 

From other bottom up specifications experience, we can envision that we'll come up first with a version that will cover chat bot requirements, and then work future versions incorporating more advanced requirements for chat bots and audio/video bots.

We value community feedbacks and will leverage github issues for the purpose of receiving feedbacks and doing arbitrations to move forward the specifications.

The botcommons specifications is composed of this background document, a set of use-cases and core specifications.


## A bit of history

This initiative started from the [node-sparkbot]() framework where an enriched healthcheck was exposed to serve several debugging and diagnose purposes: know the bot is running ok, reachable from the internet, check the identity the bot is running against, and the notifications he can listen to. 

Over time, extra metadata were added in the larger perspective to serve the bot industry by sharing common practices, and eventually come up with some universal tooling that could be run among bot platforms.

We shared these thoughts at several developer conferences (CodeMotion Milan, Rome, Amsterdam and DevNetCreate), and finally saw enough interest from various bot community members to start writing down a first draft.

The Swagger and APICommons specifications are seen as inspiring specifications from the documentation purpose they serve, but also their start small / thinkg big approach to iterate over specifictions.


## Terminoloy

### Bot

We define hereafter a bot as a piece of software that humans interact with through textual messages or voice.

Typically a bot will push its interactions via a physical device used by humans whether a Phone (voice calls and SMS), a smartphone or laptop (via rich chatting systems, possibly with Audio & Video capabilities) or any other material equiped with a piece of software (think of an ear device).


### Media & Channels

The media used by the bot to communicate with an end-user.

A bot could support several media so that it can be exploited from several chat, audio or Video platforms.

For each media, the bot can interact through one or several channels qualitied as Media Channels. Whereas most devices allow only simultaneous video or audio channel, messaging platforms let users and bots echange on several channels simultaneously (and generally asynchronously).
