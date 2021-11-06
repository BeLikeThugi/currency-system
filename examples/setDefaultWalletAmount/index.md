# cs.setDefaultWalletAmount()
Put this in Index.js
```js
// require these at top of index.js
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
// Method:
cs.setDefaultWalletAmount('100') // $100 will be default wallet money when a new User is created.
```
[`Click me to view Example Bot`](https://github.com/BIntelligent/currency-system/tree/main/v12-ExampleBot) <br><br>
<a href="https://bintelligent.github.io/currency-system/examples/setMongoURL" class="button"><- Back</a>
<a href="https://bintelligent.github.io/currency-system/examples/setDefaultBankAmount" class="button">Next -></a> <br><br><br>
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
