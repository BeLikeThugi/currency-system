# cs.info()
```js
 let result = await cs.info(message.author.id, message.guild.id);
    const embed = new Discord.MessageEmbed()
        .setDescription('Info about ' + message.author.tag);
        let unUsed = '';
        let cantBeUsed = '';
        for (const [key, value] of result.info) {
            if (value.used) unUsed += `- ${key}\n`;
            else cantBeUsed += `- ${key} ( ${value.timeLeft} )\n`;
        }
        embed.addField('Commands That you can use:', unUsed || 'None');
        embed.addField('Commands That you can\'t use:', cantBeUsed || 'None');
```
## Example
```js
    const Discord = require('discord.js')
    const CurrencySystem = require("currency-system");
    const cs = new CurrencySystem;
    let result = await cs.info(message.author.id, message.guild.id);
    const embed = new Discord.MessageEmbed()
        .setDescription('Info about ' + message.author.tag);
        let unUsed = '';
        let cantBeUsed = '';
        for (const [key, value] of result.info) {
            if (value.used) unUsed += `- ${key}\n`;
            else cantBeUsed += `- ${key} ( ${value.timeLeft} )\n`;
        }
        embed.addField('Commands That you can use:', unUsed || 'None');
        embed.addField('Commands That you can\'t use:', cantBeUsed || 'None');
    message.channel.send(embed)
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/removeUserItem" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/" class="button">Home</a> <br><br><br>
<style>
.button {
    -webkit-appearance: button;
    -moz-appearance: button;
    appearance: button;
    text-align: center;
    text-decoration: none;
    color: initial;
}
 </style>
