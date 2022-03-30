![npm install](https://nodei.co/npm/vcodes.js.png?mini=false)<br/>
[Do you need my help? Visit our Discord server.](https://vcodes.xyz/discord)

# Installation
```console
npm i vcodes.js --save
yarn add vcodes.js
```


# Usage
```js
const vCodes = require('./vcodes.index');
const dbl = new vCodes("vCodes Bot Token");


dbl.on("ready", (bot) => {
    console.log(`Bot named ${bot.username} successfully finded on vCodes.`)
    dbl.checkVote("714451348212678658").then(value => console.log("Vote Control: "+ value))

    /*
        let guildCount = 1234;
        let shardCount = 5;
        dbl.stats(guildCount, shardCount, () => console.log("Stats updated on vCodes."));
    */
})


/*
    Get with Bot: 
    dbl.on("vote", ({ user, bot }) => {
        console.log(`${user.username} voted ${bot.username}`)
    })
*/
dbl.on("vote", ({ user }) => {
    console.log(`${user.username} voted.`)
})
```

# Detailed

### Define Module
```js
const vCodes = require('./vcodes.index');
const dbl = new vCodes("vCodes Bot Token");
```

### Let's add an event to see if it works.
```js
dbl.on("ready", (bot) => {
    console.log(`Bot named ${bot.username} successfully finded on vCodes.`)
})

// => Bot named Allegro successfully finded on vCodes.
```

### Let's update bot data
```js
dbl.on("ready", (bot) => {
    console.log(`Bot named ${bot.username} successfully finded on vCodes.`)
    let guildCount = 1234;
    let shardCount = 5;
    dbl.stats(guildCount, shardCount, () => console.log("Stats updated on vCodes."));
})

// => Bot named Allegro successfully finded on vCodes.
// => Stats updated on vCodes.
```

### Let's check if a user has voted.
```js
dbl.on("ready", (bot) => {
    console.log(`Bot named ${bot.username} successfully finded on vCodes.`)
    dbl.checkVote("714451348212678658").then(value => console.log("Vote Control: "+ value))

    /*
        let guildCount = 1234;
        let shardCount = 5;
        dbl.stats(guildCount, shardCount, () => console.log("Stats updated on vCodes."));
    */
})

// => Bot named Allegro successfully finded on vCodes.
// => Vote Control: false
```

### Let's check if there is a user who voted for our bot instantly.
```js
dbl.on("vote", ({ user }) => {
    console.log(`${user.username} voted.`)
})

// => clqu voted.
```
```js
// WITH BOT
dbl.on("vote", ({ user, bot }) => {
    console.log(`${user.username} voted ${bot.username}`)
})

// => clqu voted Allegro.
```

---
<h6 align="center">Developed with ❤️ by Void Development</h6>
