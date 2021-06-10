# cs.rob()
```js
// Requiring the Package
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.rob({
        user: message.author, // user,
        user2: user, //user 2
        guild: message.guild, // guild, remove this line to make it global
        minAmount: 100, // min amount needed to rob a person.
        successPercentage: 5, // every 100 robs 5 will be sucessful
        replies: ['Programmer', 'Builder', 'Waiter', 'Busboy', 'Chief', 'Mechanic'], // replies
        cooldown: 25 //25 seconds,

    });
```
## Example
```js
let user;
        if (message.mentions.users.first()) {
            user = message.mentions.users.first();
        } else if (args[0]) {
            user = message.guild.members.cache.get(args[0]);
            if (user) user = user.user;;
        }

        if (user.bot || user === client.user) return message.channel.send("This user is a bot.");
        if (!user) return message.channel.send('Sorry, you forgot to mention somebody.');

        let result = await cs.rob({
            user: message.author,
            user2: user,
            guild: message.guild,
            minAmount: 100,
            successPercentage: 5,
            cooldown: 25 //25 seconds
        });
        if (result.error) {
            if (result.type === 'time') return message.channel.send(`You have already robbed recently Try again in ${result.time}`);
            if (result.type === 'low-money') return message.channel.send(`You need atleast $${result.minAmount} to rob somebody.`);
            if (result.type === 'low-wallet') return message.channel.send(`${result.user2.username} have less than $${result.minAmount} to rob.`)
            if (result.type === 'caught') return message.channel.send(`${message.author.username} you robbed ${result.user2.username} and got caught and you payed ${result.amount} to ${result.user2.username}!`)
        } else {
            if (result.type === 'success') return message.channel.send(`${message.author.username} you robbed ${result.user2.username} and got away with ${result.amount}!`)

        }
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/work" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/beg" class="button">Next -></a> <br><br><br>
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
