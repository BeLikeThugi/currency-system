# cs.transferMoney()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.transferMoney({
            user: message.author, // User
            guild: message.guild, // guild, Remove this line to make it global!,
            amount: money, // amount of money
            user2: user, // 2nd user
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
        } else {
            user.id = "1"
        }

        if (user.bot || user === client.user) return message.channel.send("This user is a bot.");
        if (!client.users.cache.get(user.id) || !user) return message.channel.send('Sorry, you forgot to mention somebody.');

        let amount = args[1];
        if (!amount) return message.channel.send("Enter amount of money to add.");
        if (amount.includes("-")) return message.channel.send("You can't send negitive money.")
        let money = parseInt(amount);

        let result = await cs.transferMoney({
            user: message.author,
            user2: user,
            guild: message.guild,
            amount: money
        });
        if (result.error) return message.channel.send(`You don't have enough money in your wallet.`);
        else message.channel.send(`**${message.author.username}**, Successfully transfered **${result.money}** to **${result.user2.username}**`)

```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/balance" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/leaderboard" class="button">Next -></a> <br><br><br>
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
