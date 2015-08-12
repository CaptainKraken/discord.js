# discord.js
Discord.js is a node module that allows you to interface with the [Discord](https://discordapp.com/) API for creation of things such as bots or loggers.

The aim of this API is to make it *really* simple to start developing your bots. This API has server, channel and user tracking, as well as tools to make identification really simple.

**[For more information, click here.](https://github.com/hydrabolt/discord.js/wiki)**

### Installation
``npm install discord.js``

### Example usage
```js
/*
 * A basic bot that shows how to connect to a Discord account,
 * how to listen to messages and how to send messages.
 *
 * This bot responds to every "ping" message with a "pong".
 */

var Discord = require( "discord.js" );

// Create the bot
var myBot = new Discord.Client();

// Login with an example email and password
myBot.login( "hello@example.com", "password1" );

// The "ready" event is triggered after the bot successfully connected to
// Discord and is ready to send messages.
myBot.on( "ready", function() {
	console.log( "Bot connected successfully." );
} );

// Add a listener to the "message" event, which triggers upon receiving
// any message
myBot.on( "message", function( message ) {
	// message.content accesses the content of the message as a string.
	// If it is equal to "ping", then the bot should respond with "pong".
	if ( message.content === "ping" ) {
		// Send a message ("pong") to the channel the message was sent in,
		// which is accessed by message.channel.
		this.sendMessage( message.channel, "pong" );
	}
} );
```
### TODO
* Documentation
* Better error handling
* Being able to cache new servers and channels as well as ones that are deleted - this is currently only done when a bot is created
