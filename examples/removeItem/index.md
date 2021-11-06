# cs.removeItem()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.removeItem({
        guild: message.guild, // guild, remove this line to make it global
        item: 1 // it will rmeove 1st item in shop!
    });
```
## Example
```js
    if (!args[0]) return message.channel.send('Which item to remove?')
    let result = await cs.removeItem({
        guild: message.guild,
        item: parseInt(args[0])
    });
    if (result.error) {
        if (result.type == 'Invalid-Item-Number') return message.channel.send('There was a error, Please enter item number to remove.!')
        if (result.type == 'Unknown-Item') return message.channel.send('There was a error, The Item Does not exist!')
    } else message.channel.send('Done! Successfully removed the `' + result.inventory.name + '` from shop!')
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/v12-ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/addItem" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/setItems" class="button">Next -></a> <br><br><br>
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
