# cs.removeUserItem()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
        cs.removeUserItem({
        user: message.author, // user
        guild: message.guild, // guild, remove this line to make it global
        item: 1 // item number to sell 

    }).then(console.log)
```
## Example
```js
    if (!args[0]) return message.channel.send('Which item to remove?')
    let result = await cs.removeUserItem({
        user: message.author,
        guild: message.guild,
        item: parseInt(args[0])
    });
    if (result.error) {
        if (result.type == 'Invalid-Item-Number') return message.channel.send('There was a error, Please enter item number to remove.!')
        if (result.type == 'Unknown-Item') return message.channel.send('There was a error, The Item Does not exist!')
    } else message.channel.send('Done! Successfully sold the `' + result.inventory.name + '` for free! You now have ' + result.inventory.amount + ' of those items left!')
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/buy" class="button"><- Back</a>
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
