# AI Debate Council – selector feed

This repository hosts the signed selector configuration used by the AI Debate Council Chrome extension.

- `v1/selectors.json` contains CSS selectors and text patterns for the supported AI chat sites. It is **data only, no code**.
- The file is signed with ECDSA P-256. The extension verifies the signature with a public key bundled in the extension package and ignores any file that is not signed with the matching private key.
- The extension downloads this file every 6 hours and after a page-element error. The request carries no user data.

Do not edit `v1/selectors.json` by hand: any change breaks the signature and the extension will ignore it. New versions are produced with `npm run feed:publish` in the extension repository.
