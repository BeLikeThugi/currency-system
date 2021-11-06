# cs.addItem()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.addItem({
        guild: message.guild, // guild, remove this line to make it global
        inventory: {
            name: 'Rolex', // item name
            price: 10000 // item price
        }
    });
```
## Example
```js
message.channel.send('What should be item name?');
    let Name = await message.channel.awaitMessages(msg => msg.author.id == message.author.id, {
        max: 1
    });

    message.channel.send('What should be its price?');
    let Price = await message.channel.awaitMessages(msg => msg.author.id == message.author.id, {
        max: 1
    });
    let result = await cs.addItem({
        guild: message.guild,
        inventory: {
            name: Name.first().content,
            price: parseInt(Price.first().content)
        }
    });
    if (result.error) {
        if (result.type == 'No-Inventory-Name') return message.channel.send('There was a error, Please enter item name to removadd.!')
        if (result.type == 'Invalid-Inventory-Price') return message.channel.send('There was a error, invalid price!')
        if (result.type == 'No-Inventory-Price') return message.channel.send('There was a error, You didnt specify price!')
        if (result.type == 'No-Inventory') return message.channel.send('There was a error, No data recieved!')
    } else message.channel.send('Done! Successfully added `' + Name.first().content + '` to the shop!')
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/v12-ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/getShopItems" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/removeItem" class="button">Next -></a> <br><br><br>
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
