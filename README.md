const Discord = require('discord.js');
const client = new Discord.Client();
const config = require("./config.json");

client.on('ready', () => {
  console.log("Bot Online und Fertig!");
});


client.on('message', message => {
  if(message.author.bot) return;
  if(!message.content.startsWith(config.prefix)) return;

  let command = message.content.split(" ")[0];
  command = command.slice(config.prefix.length);

  let args = message.content.split(" ").slice(1);

  if (command === "add") {
    let numArray = args.map(n => parseInt(n));
    let total = numArray.reduce( (p, c) => p+c);
    message.channel.sendMessage(total);
  }

  if (command === "yt") {
    message.channel.sendMessage("http://www.youtube.de/user/dqmhose")
  }

  if (command === "youtube") {
    message.channel.sendMessage("http://www.youtube.de/user/dqmhose")
  }

  if (command === "twitch") {
    message.channel.sendMessage("http://www.twitch.tv/xdqmhose")
  }

  if (command === "twitter") {
    message.channel.sendMessage("http://www.twitter.com/dqmhose")
  }
  if (command === "regeln") {
    message.channel.sendMessage("#willkommen")
  }
});

client.login(config.token);
