# Use cases

We list hereafter use cases that will help move forward the BotCommons specifications.
To align with the original goals of the specifications, these use-cases cover the concerns of bots end-users.


## Is the bot down ?

There are several reasons why a bot would not be responding: 
- the bot itself is not responsive,
- the messaging platform encounters a technical issue so that messages are not routed to the bot,
- the end-user or the messaging client encounters connectivity issues.

By exposing a public GET HTTP endpoint (aka healtcheck), bots could inform humans, messaging platforms and bot registries more efficiently.


## Who is the legal owner of the bot and what are the usage terms ?

This is a major convern, as today most bots don't provide usage agreement, nor display policies for the data exchange during interactions between the end-users and the bot.

If exposed through metadata, these information could be queried and versionned, but also 3rd party tools could keep track of invidual user acknowledgment.


## Which version of the bot is running, and were there any new versions pushed recently ?

When interacting with the bot, users are using the current version in production,
and may wonder about changes since last time they interacted with the bot.

This requirement could be provided by the bot itself or through the analysis of metadata. 
- bot itself: the bot would push changes as they happen through one-one messages,
- metadata: the user could ask for the history of changes


## How can I send feedback to the bot authors ?

What if an end-user wants to propose enhancements or push issues about an existing bot ?
Bots could promote a way to contact the individual or team supporting it.
Contact may be eastablished via bot commands, email or a web page.
