## Example
```js
   const CurrencySystem = require("currency-system");
   const cs = new CurrencySystem;

   let item = args[0];
   if (!item) return message.channel.send("What item you wana use?")
   const arr = await cs.getUserItems({
       user: message.author
   })
   for (i in arr.inventory) {
       if (arr.inventory[i].name.toLowerCase().includes(item.toLowerCase())) {
           const money = Math.floor((Math.random() * 10) + 1) * 100 // 100 - 1000
           i++
           const removeItem = await cs.removeUserItem({
               user: message.author,
               item: i
           });
           if (removeItem.error) {
               console.log(removeItem)
               console.log('Bot tried to remove item number ' + i)
               return message.channel.send("Unknown error occured see console.")
           }
           const result = await cs.addMoney({
               user: message.author,
               amount: money,
               wheretoPutMoney: 'wallet'
           });
           if (result.error) {
               console.log(result)
               return message.channel.send("Unknown error occured see console.")
           } else return message.channel.send("You've used " + item + " to play games and earned " + money)

       } else return message.channel.send("buy it")
   };
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/ExampleBot) <br><br>
<!-- 
<a href="https://bintelligent.github.io/currency-system/examples/custom/" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/custom/" class="button">Next -></a> <br><br><br>
<style>
.button {
    -webkit-appearance: button;
    -moz-appearance: button;
    appearance: button;
    text-align: center;
    text-decoration: none;
    color: initial;
}
 </style> -->
