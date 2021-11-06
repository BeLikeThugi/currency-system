# cs.deposite()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.deposite({
            user: message.author, // User who will deposite money to bank!
            guild: message.guild, // guild, Remove this line to make it global!
            amount: money // Amount of money!
    });
```
## Example
```js
    const CurrencySystem = require("currency-system");
    const cs = new CurrencySystem;
    let money = args.join(" ");
    if (!money) return message.channel.send("Enter the amount you want to deposite.");

    let result = await cs.deposite({
            user: message.author,
            guild: message.guild,
            amount: money
    });
    if (result.error) {
    if (result.type === 'money') return message.channel.send("Specify an amount to deposite");
    if (result.type === 'negative-money') return message.channel.send("You can't deposite negative money");
    if (result.type === 'low-money') return message.channel.send("You don't have that much money in wallet.");
    if (result.type === 'no-money') return message.channel.send("You don't have any money to deposite");
    } else {
    if (result.type === 'all-success') return message.channel.send("You have deposited all your money to your bank");
    if (result.type === 'success') return message.channel.send(`You have deposited $${result.amount} money to your bank.`);
      };
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/v12-ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/gamble" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/withdraw" class="button">Next -></a> <br><br><br>
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
