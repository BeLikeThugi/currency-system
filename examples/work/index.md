# cs.work()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.monthly({
        user: message.author, // user
        guild: message.guild, // guild, remove this line to make it global
        maxAmount: 100, // max earnable money
        replies: ['Programmer', 'Builder', 'Waiter', 'Busboy', 'Chief', 'Mechanic'], // replies
        cooldown: 25 //25 seconds,

    });
```
## Example
```js
 let result = await cs.work({
            user: message.author,
            guild: message.guild,
            maxAmount: 100,
            replies: ['Programmer', 'Builder', 'Waiter', 'Busboy', 'Chief', 'Mechanic'],
            cooldown: 25 //25 seconds,

        });
        if (result.error) return message.channel.send(`You have already worked recently Try again in ${result.time}`);
        else message.channel.send(`You worked as a ${result.workType} and earned $${result.amount}.`)
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/monthly" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/rob" class="button">Next -></a> <br><br><br>
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
