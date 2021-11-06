# cs.gamble()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.gamble({
        user: message.author, // The Person who is gambling.
        guild: message.guild, // guild, Remove This line to make it global!
        amount: money, // amount of money to gamble with
        minAmount: 1, // Minimum Amount of money that you can gamble with.
        cooldown: 25 //Cooldown, in this case 25 seconds
    });
```
## Example
```js
  const CurrencySystem = require("currency-system");
  const cs = new CurrencySystem;
  let money = args.join(" ");
    if (isNaN(money)) return message.channel.send("Amount is not a number.");

    let result = await cs.gamble({
        user: message.author,
        guild: message.guild,
        amount: money,
        minAmount: 1,
        cooldown: 25 //25 seconds
    });
    if (result.error) {
        if (result.type == 'amount') return message.channel.send("Please insert an amount first.");
        if (result.type == 'nan') return message.channel.send("The amount was not a number.");
        if (result.type == 'low-money') return message.channel.send(`You don't have enough money. You need ${result.neededMoney}$ more to perform the action. `);
        if (result.type == 'gamble-limit') return message.channel.send(`You don't have enough money for gambling. The minimum was $${result.minAmount}.`);
        if (result.type == 'time') return message.channel.send(`Wooo that is too fast. You need to wait **${result.second}** second(s) before you can gamble again.`);   
    } else {
        if (result.type == 'lost') return message.channel.send(`Ahh, no. You lose $${result.amount}. You've $${result.wallet} left. Good luck next time.`);
        if (result.type == 'won') return message.channel.send(`Woohoo! You won $${result.amount}! You've $${result.wallet}. Good luck, have fun!`);
    }

```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/v12-ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/removeMoney" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/deposite" class="button">Next -></a> <br><br><br>
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
