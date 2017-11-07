# Core Specifications

The core specifications define the set of metadata and how they can be accessed.


## Schema

Field Name | Type | Presence | Description
---|:---:|---:|---
[description](#botcommonsDescription) | `mardown` | _required_ | Gives information about the bot's goal, generally used as a short introduction, of one to three sentences
[url](#botcommonsURL) | `hyperlink` | _required_ |  Hyperlink to get more info about the bot. Will generally point to a Web page
[version](#botcommonsVersion) | `string` | _optional_ | Version of the bot, following the semantic version format
[legal-owner](#botcommonsLegalOwner) | `string` | _required_ |  Some information of the legal entity or individual behind the bot. The owner is responsible for user's data privacy
[contact](#botcommonsSupportContact) | `hyperlink` | _required_ |  The individual or group to reach to for feedback or support
[platform](#botcommonsPlatform) | `enum` | _required_ |  The platform where the bot is living
[identity](#botcommonsBotIdentity) | `string` | _required_ |  The identity of the bot on the platform it is living
[healthcheck](#botcommonsHealthcheck) | `hyperlink` | _optional_ | Endpoint where it can be technically checked that the API behind the bot is up
[botcommons](#botcommonsVersion) | `hyperlink` | _required_ |  version of the BotCommons specifications the present metadata conform to


### <a name="botcommonsDescription"></a> description

Give information about the bot's goal, generally used as a short introduction, of one to three sentences.

Formatted as: `mardown`

Presence: _required_

Examples:
- "YourBot is an **awesome** bot for sure!"

### <a name="botcommonsURL"></a> url

Hyperlink to get more info about the bot. 
Will generally point to a Web page.

Formatted as: `hyperlink`

Presence: _required_

Examples: 
- "https://github.com/CiscoDevNet/botkit-template"


### <a name="botcommonsVersion"></a> version

Version of the bot, following the semantic version format.

Formatted as: `string`

Presence: _optional_

Examples: 
- "0.7.0"

### <a name="botcommonsLegalOwner"></a> legal-owner

Some information of the legal entity or individual behind the bot. 
The owner is responsible for how data are used.

Formatted as: `string`

Presence: _required_

Examples: 
- "Cisco DevNet <https://developer.cisco.com>"


### <a name="botcommonsSupportContact"></a> contact

The individual or group to reach to for support.

Formatted as: `hyperlink` (mailto:// or http://)

Presence: _required_

Examples:
- "Stève Sfartz <mailto:stsfartz@cisco.com>"


### <a name="botcommonsPlatform"></a> platform

The platform where the bot is living.

Formatted as: `enum` 

Presence: _required_

Possible values: `ciscospark`, `messenger`, `msteams`, `phone`,  `slack`, `telegram`, `twitter`
(we'll strive to make this list exhaustive, please submit missing entries)


### <a name="botcommonsBotIdentity"></a> identity

The identity of the bot on the platform it is living.
Unique for the platform.

Formatted as: `string` (platform dependent)

Presence: _required_

Examples:
- "learninglab@sparkbot.io"


### <a name="botcommonsHealthcheck"></a> healthcheck

Endpoint where it can be technically checked that the bot is running

Formatted as: `hyperlink`

Presence: _required_

Examples:
- "https://botkit-template.herokuapp.com/"


### <a name="botcommonsVersion"></a> botcommons

Version of the specifications

Formatted as: `hyperlink`

Presence: _required_

Examples:
- "https://github.com/ObjectIsAdvantag/botcommons/releases/0.1.0"



## Accessing the metadata

Several ways to access the metadata have been identified:
- public **HTTP endpoints** exposed by the bot itself,
- built-in **bot commands** on the messaging platform,
- registries that would store bots metadata.

These specifications cover how the public HTTP endoints and the bot commands should be exposed in order to facilitate the emergence of a common and shared industry practices.

Public registries could be built from the HTTP endpoints and built-in bot commands.
Public registries are out of the scope of these specifications.

**To comply with the BotCommons specifications, the bot MUST provide a _public HTTP endpoint_ AND/OR a _built-in command_**


### HTTP endpoints

The bot itself MAY expose the schema as at a public HTTP endpoint, with a base path of its choice, through a GET method returning a 200 OK HTTP status code and a JSON payload containing the metadata.

If an healtcheck is provided, it MUST be through a public HTTP endpoint, via a GET method returning a 200 OK HTTP status code. The healthcheck MAY return a payload.

Example: 

> GET https://botkit-template.herokuapp.com/botcommons
>
> 200 OK

    ```json
    {
    "description": "It's an **awesome** bot for sure!",
    "url": "https://github.com/CiscoDevNet/botkit-template",
    "version": "0.7.0",
    "legal-owner": "Cisco DevNet <https://developer.cisco.com>",
    "contact": "Stève Sfartz <mailto:stsfartz@cisco.com>",
    "plaform": "ciscospark",
    "identity": "learninglab@sparkbot.io",
    "healthcheck": "https://botkit-template.herokuapp.com/",
    "botcommons": "https://github.com/ObjectIsAdvantag/botcommons/releases/0.1.0"
    }
    ```

### Bot Commands

The bot MAY propose a technical command which will return the metadata object in a JSON format.
The purpose of this command is to be exploited by bot-specific toolings.
This command MUST be named `.commons` - DOT COMMONS -.

The bot MAY propose a functional command for the user to inquire about the bot metadata.
The preferred name for this command is `about`.
The output of the command is not specified as the current version of the specification.
