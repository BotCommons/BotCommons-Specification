# Core Specifications

The core specifications define the set of data, as well as how they can be accessed.


## Data

### description

Give information about the bot's goal, generally used as a short introduction, of one to three sentences.

Formatted as: mardown


### url

Hyperlink to get more info about the bot. 
Will generally point to a Web page.

Formatted as: hyperlink


### legal-owner

Some information of the legal entity or individual behind the bot. 
The owner is responsible for how data are used.

Formatted as: string


### support-contact

The individual or group to reach to for support.

Formatted as: hyperlink (mailto:// or http://)


### platform

The platform where the bot is living.

Formatted as: enum (TODO: provide a list of possible values)


### identity

The identity of the bot on the platform it is living.
Unique for the platform.

Formatted as: string (format is platform dependant)


### healthcheck

Endpoint where it can be technically checked that the bot is running

Formatted as: hyperlink


### botcommons

Complies with the mentionned version of the specifications.

Formatted as: hyperlink

### Data example

JSON is the default format for these data.

```json
{
  "description": "It's an awesome bot for sure!",
  "url": "https://github.com/CiscoDevNet/botkit-template",
  "legal-owner": "Cisco DevNet <https://developer.cisco.com>",
  "support-contact": "Stève Sfartz <mailto:stsfartz@cisco.com>",
  "plaform": "ciscospark",
  "identity": "learninglab@sparkbot.io",
  "healthcheck": "https://botkit-template.herokuapp.com/",
  "botcommons": "https://github.com/ObjectIsAdvantag/botcommons/releases/v0.1"
}
```


## Exposure

The specifications do not assume a specific way to expose the botcommons metadata.
Several media have been identified:
- a public HTTP endpoint,
- a bot command exposed on the messaging platform
- a database that would store multiple bot specifications

The specification documents how the public HTTP endoint and the bot command should be exposed in order to facilitate the emergence of a common and shared industry practices.


### HTTP endpoint

### Native Bot Command

We would like to have the bot give us some meta info about himself.

For that to happen, the bot will expose a `.commons` command.

The command will return a subset of the botcommons metadata, as well as a link to the full set of metadata.

This subset of metadata, can be returned in 
Bot command subset of metadata

### Database

Not covered by the specifications.
