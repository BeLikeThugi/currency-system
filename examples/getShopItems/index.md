# cs.getShopItems()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.getShopItems({
        guild: message.guild, // guild, remove this line to make it global
    });
```
## Example
```js
    let result = await cs.getShopItems({
        guild: message.guild
    });
    let inv = result.inventory;
    const embed = new Discord.MessageEmbed()
        .setDescription('Shop!')
    for (let key in inv) {
        embed.addField(`${parseInt(key) + 1} - **${inv[key].name}:**`, `Price: ${inv[key].price}`)
    }
    message.channel.send(embed)
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/v12-ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/getUserItems" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/addItem" class="button">Next -></a> <br><br><br>
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
