# Facebot

Facebot is a [Slack](https://slack.com/) bot for facebook messenger integration. It allows you to link slack channels to facebook messenger, and communicate to them through slack.

## Features
- Connect slack channel to a facebook messenger channels
- Messages appear using friends names and profile pictures
- Supports all message types: Images, Stickers, Gifs, Thumbs & Audio messages
- Emoji support

### Restrictions
- Only 1 facebook account can login and is authorised to use the bot. Multi-user support could be added in the future but facebook-chat-api requires logins to use plaintext email and password, so these are passed and environment variables for a single account.
- For privacy, you can only link completely private slack channels (just you and facebot) to messenger. The person you want to link must be a facebook friend.

# Running the bot

## Installing
You can download the package from npm with
`npm install facebot`

## Environment Variables

However you choose to run the bot, you will need to set these environment variables below:

Variable|Description
----|-----
`BOT_API_KEY`|The slack bot API key, for the bot user you want to run facebot
`BOT_NAME`|The name of your slack bot
`AUTHORISED_USERNAME`|The slack username for the authorised user. The authorised user should be the owner of the Facebook account. Only the authorised user can interact with Facebot (link channels etc).
`FACEBOOK_EMAIL`|Email address for the Facebook account you want to use
`FACEBOOK_PASSWORD`|Password for the Facebook account you want to use
`POSTGRES_DB_URL`|URL for a postgres database to save and load data from. This reduces the number of sign in messages you may receive by using existing cookies and tokens, and keeps channel links persistent through bot restarts. **If this is not set** the bot will still function, but you will lose channel links between sessions.
`DEBUG_MESSAGES`|False by default. Set this to true to receive debug direct messages from Facebot 

## Running Locally
You can test and run Facebot locally by `node bin/run_local_storage.js`

You will still need to setup the environment variables described above (without `POSTGRES_DB_URL`).

## Deploying to Heroku
