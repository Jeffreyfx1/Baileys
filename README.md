
# Baileys — Typescript/Javascript WhatsApp Web API

<div align="center">
  <img src="https://files.catbox.moe/07u3zy.jpg" alt="Baileys Header" width="100%"/>
</div>

Baileys is a Typescript/Javascript library that implements the WhatsApp Web protocol. This fork/package re-exports the library under the package name `veron-baileys` so you can install it either using the stable unscoped name or via the original scoped names that point to this package.

Package on npm: https://www.npmjs.com/package/veron-baileys  
Homepage / source: https://github.com/VeronDev/Baileys

Badges
- npm: veron-baileys (latest)
- Compatible aliases:
  - `@whiskeysockets/baileys` => `npm:veron-baileys@latest`
  - `@adiwajshing/baileys` => `npm:veron-baileys@latest`

Quick install

Using Yarn (recommended)
```bash
yarn add veron-baileys
# or pin a specific version:
yarn add veron-baileys@1.0.2
```

Using npm
```bash
npm install veron-baileys
# or pin a specific version:
npm install veron-baileys@1.0.2
```

If you want to use the original package names as aliases in package.json, add these entries:
```json
{
  "dependencies": {
    "@whiskeysockets/baileys": "npm:veron-baileys@latest",
    "@adiwajshing/baileys": "npm:veron-baileys@latest",
    "veron-baileys": "1.0.2"
  }
}
```

Importing

If you installed the unscoped package:
```ts
import makeWASocket from 'veron-baileys'
```

If you used one of the aliased scoped package names, import exactly as you would normally:
```ts
import makeWASocket from '@whiskeysockets/baileys'
// or
import makeWASocket from '@adiwajshing/baileys'
```

Minimal example

This is a compact example showing how to create a socket and listen for connection updates. For a fuller example that covers authentication, message handling, media, and reconnection, see the included example.ts file in the repository.

```ts
import makeWASocket from 'veron-baileys'

async function start() {
  const sock = makeWASocket({
    // pass options here (logger, printQRInTerminal, auth, etc.)
  })

  sock.ev.on('connection.update', (update) => {
    console.log('connection update:', update)
  })

  sock.ev.on('messages.upsert', (m) => {
    console.log('messages upsert:', m)
  })
}

start().catch(console.error)
```

Running the example

1. Clone or download the repository:
   ```bash
   git clone https://github.com/VeronDev/Baileys.git
   cd Baileys
   ```
2. Install dependencies:
   ```bash
   yarn
   ```
3. Run the example script:
   ```bash
   yarn example
   ```

Notes and compatibility
- This package re-exports the Baileys API under the `veron-baileys` package name. If you depend on code that imports `@whiskeysockets/baileys` or `@adiwajshing/baileys`, you can use the alias entries above in package.json so existing imports continue to work.
- Check example.ts in the Example/ folder for a full demonstration of usage patterns, session persistence, message handling, and media upload/download.
- Keep your environment up-to-date with Node.js LTS releases for best compatibility.

Contributing
- Contributions, bug reports, and PRs are welcome. Please open issues or pull requests on the GitHub repository: https://github.com/VeronDev/Baileys

License
- See LICENSE in the repository for license details.
