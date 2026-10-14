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

| `house_id` | House      | Preview                                  |
|:----------:|:----------:|:----------------------------------------:|
| 1          | Bravery    | ![Bravery](images/bravery.png)           |
| 2          | Brilliance | ![Brilliance](images/brilliance.png)     |
| 3          | Balance    | ![Balance](images/balance.png)           |

---

![All HypeSquad badges](images/badges.png)
