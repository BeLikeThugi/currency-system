# cs.beg()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.beg({
        user: message.author, // user,
        guild: message.guild, // guild, remove this line to make it global
        minAmount: 100, // min amount you earn after begging.
        maxAmount: 400 // max amount you earn after begging.
    });
```
## Example
```js
    let result = await cs.beg({
        user: message.author,
        guild: message.guild,
        minAmount: 100,
        maxAmount: 400

    });
    if (result.error) return message.channel.send(`You have begged recently Try again in ${result.time}`);
    else message.channel.send(`You have earned $${result.amount}.`)
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/rob" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/getUserItems" class="button">Next -></a> <br><br><br>
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
