# cs.addMoney()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
 cs.removeMoney({
            user: user, // User
            guild: message.guild, // Guild
            amount: '100', //  amount of money
            wheretoPutMoney: 'bank' // or 'wallet'
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
        if (user) user = user.user;;
    } else if (!args[0]) {
        return message.channel.send("Specify a user!");
    }
    if (!message.member.hasPermission('ADMINISTRATOR')) return message.channel.send("You do not have requied permissions.")
    let wheretoPutMoney = args[2] || "wallet"; //or bank
    let amount = args[1];
    if (!amount) return message.channel.send("Enter amount of money to Remove.");
    let money = parseInt(amount);
    let result = await cs.removeMoney({
        user: user,
        guild: message.guild,
        amount: money,
        wheretoPutMoney: wheretoPutMoney
    });
    if (result.error) return message.channel.send("You cant Remove negitive money");
    else message.channel.send(`Successfully Removed $${money} to ${user.username}, ( in ${wheretoPutMoney} )`)

```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/setDefaultBankAmount" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/removeMoney" class="button">Next -></a> <br><br><br>
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
