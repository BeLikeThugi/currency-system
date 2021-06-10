  <h1>Currency-System</h1>
  <p>
    <a href="https://www.npmjs.com/package/currency-system"><img src="https://img.shields.io/npm/v/currency-system?maxAge=3600" alt="NPM version" /></a>
    <a href="https://www.npmjs.com/package/currency-system"><img src="https://img.shields.io/npm/dt/currency-system?maxAge=3600" alt="NPM downloads" /></a>
  </p>
  <p>
    <a href="https://www.npmjs.com/package/currency-system"><img src="https://nodei.co/npm/currency-system.png?downloads=true&stars=true" alt="NPM Banner"></a>
  </p>
  

  
  # 📂 | Installation
```sh
npm i currency-system
```

# 📰 | Setup
```js
const CurrencySystem = require("currency-system");
const cs = new CurrencySystem;
//sets mongo url
cs.setMongoURL("MONGO URL");
//sets default wallet amount when ever new user is created.
cs.setDefaultWalletAmount('100');
//sets default bank amount when ever new user is created.
cs.setDefaultBankAmount('1000');
```

# ✍️ | Examples
See [Examples](https://bintelligent.github.io/currency-system/examples)
