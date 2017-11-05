# Use cases

We list hereafter use cases that will help move forward the BotCommons specifications.

## Is the bot down ?

There are several reasons why a bot would not be responding: 
- the bot itself is not responsive
- the messaging platform encounters a technical issue so that messages are not routed to the bot,
- the end-user or the messaging client encounters connectivity issues


## Who is the legal owner of the bot and what are the usage terms ?

This is a major convern, as today most bots don't provide usage agreement, nor display policies for the data exchange during interactions between the end-users and the bot.

If exposed through metadata, these information could be queried and versionned, but also 3rd party tools could keep track of invidual user acknowledgment.


## Which version of the bot is running, and were there any new version pushed recently ?

When interacting with the bot, users are using the current version in production,
and may wonder about changes since last time they interacted with the bot.

This requirement could be provided by the bot itself or through the analysis of metadata. 
- bot itself: the bot would push changes as they happen through one-one messages,
- metadata: the user could ask for the history of changes


## How can I send feedback to the bot author ?

what if an end-user wants to propose enhancements or push tickets about an existing bot ?
The bot would need to propose a way to contact its author or the team supporting it.
