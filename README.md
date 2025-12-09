Jephter-Bailey’s — Typescript/Javascript WhatsApp Web API
<div align="center"> <img src="https://i.ibb.co/4wHk2CRf/wp10819318.jpg" alt="Baileys Header" width="100%"/> </div>

Jephter-Bailey’s is a Typescript/Javascript library that implements the WhatsApp Web protocol.
This fork/package re-exports the library under the package name jephter-baileys, allowing you to install it directly or use compatible scoped aliases pointing to this package.

Package on npm: (Add link after publishing)
Homepage / Source: https://github.com/Jeffreyfx1/Baileys

Badges

npm: jephter-baileys (latest)

Compatible aliases:

@whiskeysockets/baileys → npm:jephter-baileys@latest

@adiwajshing/baileys → npm:jephter-baileys@latest

Quick Install
Using Yarn (recommended)
yarn add jephter-baileys
# or pin a specific version:
yarn add jephter-baileys@1.0.0

Using npm
npm install jephter-baileys
# or pin a specific version:
npm install jephter-baileys@1.0.0

Using package aliases

Add these entries to your package.json if you want older package names to point to this fork:

{
  "dependencies": {
    "@whiskeysockets/baileys": "npm:jephter-baileys@latest",
    "@adiwajshing/baileys": "npm:jephter-baileys@latest",
    "jephter-baileys": "1.0.0"
  }
}

Importing
If you installed the unscoped package:
import makeWASocket from 'jephter-baileys'

If you used the aliased scoped package names:
import makeWASocket from '@whiskeysockets/baileys'
// or
import makeWASocket from '@adiwajshing/baileys'

Minimal Example

Below is a compact example showing how to create a socket and listen for connection updates.

import makeWASocket from 'jephter-baileys'

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

Running the Example

Clone or download the repository:

git clone https://github.com/Jeffreyfx1/Baileys.git
cd Baileys


Install dependencies:

yarn


Run the example script:

yarn example

Notes & Compatibility

This package re-exports the Baileys API under jephter-baileys.

If you depend on code that imports @whiskeysockets/baileys or @adiwajshing/baileys, use the alias entries in package.json so you don’t need to change existing imports.

Check example.ts in the repository for a full demonstration of:

authentication & session persistence

message sending/receiving

media upload/download

reconnection logic

event handling

Ensure your Node.js environment is up-to-date with the latest LTS release to ensure compatibility.

Contributing

Contributions, bug reports, and pull requests are welcome.
Please open issues or PRs on the GitHub repository:

https://github.com/Jeffreyfx1/Baileys

License

See the LICENSE file in the repository for full license details.
