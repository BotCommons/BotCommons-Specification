# BotCommons: metadata for bots

## Introduction

Lack of common industry practices makes it difficult to inform end-users efficiently (regarding bot usage terms, feedback submission or point of contact for support) as well as implement tooling for bots (such as discovery, versions transitioning, bot status checks).

BotCommons is a project to fill these [gaps in Bots User's Experience](UseCases.md) via [bot design practices and standardized metadata](BotCommons.md) to facilitate the creation of cross-platforms automated tooling for bots.


## Principles

This effort is lead from the bottom up: the proposed practices and metadata are incrementally grown from real-world end-users concerns documented via use cases.

We will thrive to keep backward compatibility but won't make it a first priority as the overgoal is to make botcommons cover most commons industry scenarios. 

From other bottom up specifications experience, we can envision that we'll come up first with a version that will cover chat bot requirements, and then work future versions incorporating more advanced requirements for chat bots and audio/video bots.

We value community feedbacks and will leverage github issues for the purpose of receiving feedbacks and doing arbitrations to move forward the specifications.

The botcommons specifications is composed of this background document, [use-cases](UseCases.md) and [core specifications](BotCommons.md).


## A bit of history

This initiative started from the [node-sparkbot](https://github.com/CiscoDevNet/node-sparkbot#healthcheck) framework where an enriched healthcheck was exposed for debugging and diagnose purposes: check the bot is running ok, reachable from the internet, display the identity the code is running against, and the set of notifications implemented by the bot.

Over time, extra metadata were added in the larger perspective to serve the bot industry by sharing common practices, and eventually come up with some universal tooling that could be run among bot platforms. A new implementation got proposed for [botkit](https://github.com/CiscoDevNet/botkit-ciscospark-samples/blob/master/template/bot.js#L47). This implementation then evolved to separate concerns: 
- from [publishing some metadata](https://github.com/CiscoDevNet/botkit-template/blob/plugin/plugins/botcommons.js), 
- to exposing an [healthcheck endpoint](https://github.com/CiscoDevNet/botkit-template/blob/plugin/plugins/healthcheck.js),
- and proposing a [built-in bot command](https://github.com/CiscoDevNet/botkit-template/blob/plugin/skills/about.js).

We shared these thoughts at several developer conferences (CodeMotion Milan, Rome, Amsterdam and DevNetCreate, Devoxx), and saw enough interest from various bot community members to start writing down a first draft.

The Swagger and APICommons specifications are seen as inspiring specifications from the documentation purpose they serve, but also their pragramtic 'Start Small / Think Big' - Bottom Up approach.


## Terminoloy

### Bot

We define hereafter a bot as a piece of software that humans interact with through textual messages or voice.

Typically a bot will push its interactions via a physical device used by humans whether a Phone (voice calls and SMS), a smartphone or laptop (via rich chatting systems, possibly with Audio & Video capabilities) or any other material equiped with a piece of software (think of an ear device).


### Media & Channels

The media used by the bot to communicate with an end-user.

A bot could support several media so that it can be exploited from several chat, audio or Video platforms.

For each media, the bot can interact through one or several channels qualitied as Media Channels. Whereas most devices allow only simultaneous video or audio channel, messaging platforms let users and bots echange on several channels simultaneously (and generally asynchronously).
