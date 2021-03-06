# hubot-jira-logger

Hubot script for logging hours on Jira.

See [`src/jira-logger.js`](src/jira-logger.js) for full documentation.

If you don't know what [Hubot](https://hubot.github.com/) is check out [this nice introduction](https://www.youtube.com/watch?v=SA1h34ESWqQ) by the guys who created it. To summarize, it's a chat bot that you can use to automate some work for you. Is normally used for what people are calling "ChatOps".

## Installation

In hubot project repo, run:

`npm install hubot-jira-logger --save`

Then add **hubot-jira-logger** to your `external-scripts.json`:

```json
[
  "hubot-jira-logger"
]
```

You will also need to set two environment variables:
* HUBOT_JIRA_PROJECT_TOKEN - Access Token for JIRA API Requests.
* HUBOT_JIRA_API_URL - The domain URL for you jira instance.

## Sample Interaction

Privately, user1 sends a message to hubot.
```
user1>> hubot auth <user1.email> <password>
hubot>> Your user was successfully added to my database.
```

If another user2 tries to add in credentials for other people.
```
user2>> hubot auth <user1.email> <password>
hubot>> <user1.email> is not your username. You can only log work with your username.
```

_It's important to notice that currently, the verification between different users is made by e-mail. So the Jira Account e-mail must match the Slack Account e-mail in order to add credentials._

Logging hours on JIRA.
```
user1>> hubot log <time> on <task> [optional-comment]
hubot>> Logged <time> on <task>.
```

**Always prefer to use these two commands in a private chat with the bot, otherwise people will see your credentials when you use the auth command. Be careful!**

## NPM Module

https://www.npmjs.com/package/hubot-jira-logger
