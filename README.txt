static-ivy — hosted games edition

Upload this entire folder to a static HTTPS host and open index.html or the
folder URL ending in /. It also works on localhost HTTP. It discovers its
base path automatically and uses hash navigation, with no SPA rewrite needed.

Games load in an isolated iframe from https://games.ivy.rest/k/index.html, the
same live library as ivy.rest, including the ivy, cloud, lumin, ugs and gn-math
sources. Lumin and cloud games run on the hosted runner.

AI, chat, billing, developers, links, settings and sign-in are the real ivy.rest
app, loaded once through the bundled proxy into a shared frame with its own
sidebar and toolbars hidden. They update whenever ivy.rest does. Settings sync
back to this page. Payment pages open outside the proxy in a new tab.

Proxy engines, WASM and transports are bundled locally. Edit wisp.json to change
the ordered WebSocket Wisp server list.

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

Google sign-in runs on this page, not inside the proxy, so this host must be
listed in Firebase authorized domains. The proxy session then stays signed in.
