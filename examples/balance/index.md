# cs.balance()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.balance({
            user: user, // User who will deposite money to bank!
            guild: message.guild, // guild, Remove this line to make it global!
    });
```
## Example
```js
    const CurrencySystem = require("currency-system");
    const cs = new CurrencySystem;
   let user;
        if (message.mentions.users.first()) {
            user = message.mentions.users.first();
        } else if (args[0]) {
            user = message.guild.members.cache.get(args[0]);
            if (user) user = user.user;
        } else if (!args[0]) {
            user = message.author;
        }

        let result = await cs.balance({
            user: user,
            guild: message.guild
        });
        message.channel.send(`${user.tag}, \n have $${result.wallet} in you wallet and $${result.bank} in there bank.`);
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/withdraw" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/transferMoney" class="button">Next -></a> <br><br><br>
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
