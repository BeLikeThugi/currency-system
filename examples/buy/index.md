# cs.buy()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
        cs.buy({
        user: message.author, // user
        guild: message.guild, // guild, remove this line to make it global
        item: 1 // item number to buy 

    }).then(console.log)
```
## Example
```js
    let thing = args[0]
    if (!thing) return message.channel.send('Please provide item number')
    if (isNaN(thing)) return message.channel.send('Please provide valid item number')
    message.channel.send(`Please type \`yes\` to confirm`)
    let col = await message.channel.awaitMessages(msg => msg.author.id == message.author.id, {
        max: 1
    });
    if (col.first().content.toLowerCase() === 'yes') {

        let result = await cs.buy({
            user: message.author,
            guild: message.guild,
            item: parseInt(args[0])
        });
        if (result.error) {
            if (result.type === 'No-Item') return message.channel.send('Please provide valid item number');
            if (result.type === 'Invalid-Item') return message.channel.send('item does not exists');
            if (result.type === 'low-money') return message.channel.send(`**You don't have enough balance to buy this item!**`);
        } else return message.channel.send(`**Successfully bought  \`${result.inventory.name}\` for $${result.inventory.price}**`)
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/v12-ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/setItem" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/removeUserItem" class="button">Next -></a> <br><br><br>
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
