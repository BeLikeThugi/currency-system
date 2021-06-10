# cs.getUserItems()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.getUserItems({
        user: message.author, // user,
        guild: message.guild, // guild, remove this line to make it global
    });
```
## Example
```js
let result = await cs.getUserItems({
        user: message.author,
        guild: message.guild,
    });
    let inv = result.inventory.slice(0,10)
    const embed = new Discord.MessageEmbed()
    .setDescription('Your Inventory!')
    for (key of inv) {
        embed.addField(`**${key.name}:**`, `Amount: ${key.amount}`)
    }
    message.channel.send(embed)
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/beg" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/getShopItems" class="button">Next -></a> <br><br><br>
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
