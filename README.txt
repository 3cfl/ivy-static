static-ivy — hosted games edition

Upload this entire folder to a static HTTPS host and open index.html or the
folder URL ending in /. It also works on localhost HTTP. It discovers its
base path automatically and uses hash navigation, with no SPA rewrite needed.

Games load in an isolated iframe from:
https://games.ivy.rest/static/games/index.html
The hosted library provides Lumin, UGS and GN-Math. Game HTML, thumbnails and
catalogues are not included in this smaller download. Games require access to
the hosted service. Existing local game-save messages remain bound to the
expected iframe source and exact game origin; saves stay on your static host.

tejmarcs/teiloivartlu, their WASM and transports remain bundled locally.
Edit wisp.json to change the ordered WebSocket Wisp server list. API base is
https://ivy.rest. Account, community chat, billing and links open through the local proxy in
internal Ivy tabs. They require their normal Ivy sign-in. Proxy sessions are
separate from direct ivy.rest sessions; sign-in and payment providers may
restrict proxied browsers. No authentication checks are disabled.

This edition uses classic browser scripts, including transport and worker
startup. No browser ES-module loader is needed for the bundled app. Websites
opened through the proxy and the hosted games service can use their own
modules. The proxy still uses bundled WASM.

Serve .js as JavaScript and .wasm as application/wasm. Service worker
scope is this folder. Avoid blanket COEP=require-corp headers because they can
block externally hosted games. HTTPS or localhost is required for the proxy.

Keep this folder structure intact. No Node process, npm install, private key,
server source, account database or runtime secret is part of this deployment.
Original dependency license notices are retained in licenses/.

The outer static dashboard does not inherit a proxied account session. Account
tools and community chat run inside their proxy tabs. Browser sign-in and
OAuth/payment flows have not been interactively verified.
