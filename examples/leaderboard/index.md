# cs.removeMoney()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.leaderboard(message.guild.id); // guild ID
```
## Example
```js
  const CurrencySystem = require("currency-system");
  const cs = new CurrencySystem;
   let data = await cs.leaderboard(message.guild.id);
    if (data.length < 1) return message.channel.send("Nobody's in leaderboard yet.");
    const msg = new Discord.MessageEmbed();
    let pos = 0;
    // This is to get First 10 Users )
    data.slice(0, 10).map(e => {
        pos++
        if (!client.users.cache.get(e.userID)) return;
        msg.addField(`${pos} - **${client.users.cache.get(e.userID).username}**`, `Wallet: **${e.wallet}** - Bank: **${e.bank}**`, true);
    });

    message.channel.send(msg).catch();
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/transferMoney" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/globleLeaderboard" class="button">Next -></a> <br><br><br>
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
