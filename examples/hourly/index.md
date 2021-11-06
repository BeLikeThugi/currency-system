# cs.hourly()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.hourly({
        user: message.author, // user
        guild: message.guild, // guild, remove this line to make it global
        amount: 100, // amount to give when user run this command

    });
```
## Example
```js
let result = await cs.hourly({
        user: message.author,
        guild: message.guild,
        amount: 100,

    });
    if (result.error) return message.channel.send(`You have used hourly recently Try again in ${result.time}`);
    else message.channel.send(`You have earned $${result.amount}.`)
}
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/v12-ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/globalLeaderboard" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/quaterly" class="button">Next -></a> <br><br><br>
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
