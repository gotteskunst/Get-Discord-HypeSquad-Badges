# Get HypeSquad Badges (really, not client-sided)

Get your Discord HypeSquad badge straight from Discord's own API. The badge is really added to your account and is not just a visual trick on your screen.

## Quick start

1. Open Discord in your browser or in the desktop app.
2. Open the developer tools:
   > **Browser:** `F12`  |  **Desktop app:** `Ctrl + Shift + I`
3. Go to the **Console** tab, paste this script, and hit Enter:

```js
const req = webpackChunkdiscord_app.push([[Symbol()], {}, r => r]);
webpackChunkdiscord_app.pop();

const modules = Object.entries(req.m);

const loadModuleContaining = (...snippets) => {
    for (const [id, factory] of modules) {
        const source = factory.toString();
        if (snippets.every(s => source.includes(s))) return req(id);
    }
};

const http = Object.values(loadModuleContaining("HTTPUtils")).find(m => m?.get);

http.post({ url: "/hypesquad/online", body: { house_id: 1 } });
```

<details>
  <summary>Console won't let you paste?</summary>

### Unlock pasting first

Discord blocks pasting in the console as a safety measure. Type one of these into the console and press Enter, then paste the script again:

```
allow pasting
```

If the first one doesn't work, try these variants one at a time:

```
"allow pasting"
```
```
'allow pasting'
```

</details>

<details>
  <summary>Want to get rid of your badge?</summary>

### Remove the badge

Paste this script into the console and your badge will be removed:

```js
const req = webpackChunkdiscord_app.push([[Symbol()], {}, r => r]);
webpackChunkdiscord_app.pop();

const modules = Object.entries(req.m);

const loadModuleContaining = (...snippets) => {
    for (const [id, factory] of modules) {
        const source = factory.toString();
        if (snippets.every(s => source.includes(s))) return req(id);
    }
};

const http = Object.values(loadModuleContaining("HTTPUtils")).find(m => m?.get);

http.del({ url: "/hypesquad/online" });
```

</details>

## Choose your badge

Edit the `house_id` in the last line of the script to receive a different badge:

| `house_id` | House      | Preview                                   |
|:----------:|:----------:|:-----------------------------------------:|
| 1          | Bravery    | ![Bravery](https://cdn.discordapp.com/attachments/1559878710222655539/1559878737850540072/bravery.png?ex=6ad0adc8&is=6acf5c48&hm=2269641ca33b708f516598137c64dbb68c033cc70be7aee6655df09af18911fa&animated=true) |
| 2          | Brilliance | ![Brilliance](https://cdn.discordapp.com/attachments/1559878710222655539/1559878725708025906/brilliance.png?ex=6ad0adc5&is=6acf5c45&hm=3aafa2d993d41a66802a0ed6a4d3ebf0303bb59481c3cc336aba22d25003aa4f&animated=true) |
| 3          | Balance    | ![Balance](https://cdn.discordapp.com/attachments/1559878710222655539/1559878749107920906/balance.png?ex=6ad0adca&is=6acf5c4a&hm=fadc5cf9695fd1342bbb5eac761ca389ea46c40de49ce9064e432ddbaf74b15d&) |

---

![All HypeSquad badges](https://cdn.discordapp.com/attachments/1559878710222655539/1559878761229590618/badges.png?ex=6ad0adcd&is=6acf5c4d&hm=7cc99ce28169d8c97afc7705bae07c58e3d815e57fb8a514a530f879055020a7)
