# HyperGhostChat

A messenger interface in a **single HTML file**. Encryption happens in the browser using the Web Crypto API &mdash; no server, no build step, no dependencies.

<p align="center"><sub>HX-E2E &middot; three sequential AES-256-GCM layers</sub></p>

## What's inside

| Layer | Detail |
| --- | --- |
| **Cipher** | `AES-GCM` 256-bit, generated with `crypto.subtle.generateKey` |
| **Layering** | Each message is encrypted, the key is encrypted, then that key is encrypted &mdash; three independent operations |
| **Key derivation** | `SHA-256` digest imported as an `AES-GCM` key |
| **Sanitising** | [DOMPurify](https://github.com/cure53/DOMPurify) is loaded before any message is rendered, so markup in a message cannot execute |

## Run it

Open `index.html` in a browser. Everything runs locally.

```bash
git clone https://github.com/hypersenseindia/HYPERGHOSTCHAT
cd HYPERGHOSTCHAT
# then open index.html
```

## Read this before trusting it

This is a **cryptography demo and UI**, not an audited messenger.

- Keys are generated and handled inside the page. There is no key exchange with a peer, no identity verification and no forward secrecy.
- Encryption is only as strong as the page that performs it. Serve it over HTTPS.
- For real end-to-end messaging use Signal, or a library such as libsodium that has been reviewed.

The AES-GCM calls themselves are real Web Crypto primitives &mdash; it is the protocol around them that is demonstrative.

## Licence

Published for reference and learning. No warranty.
---

<p align="center">
  <sub>Built by <b>AG HYDRAXFF</b> &mdash; HYPERSENSEGLOBAL &middot;
  <a href="https://www.instagram.com/hydraxff_yt/">@hydraxff_yt</a></sub>
</p>