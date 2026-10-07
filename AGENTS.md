# Documentation project instructions

## About this project

- This is the public documentation for [Passform](https://passform.io), a platform for creating, distributing, and updating Apple Wallet and Google Wallet passes
- The site is built on [Mintlify](https://mintlify.com) and published at https://docs.passform.io
- Pages are MDX files with YAML frontmatter
- Configuration and navigation live in `docs.json`
- Run `mint dev` to preview locally
- Run `mint broken-links` to check links

## API reference

- The API reference tab is generated from `api-reference/openapi.json`. Do not edit that file by hand.
- Refresh it with `npm run sync-openapi:prod`, which copies the spec from https://api.passform.io/openapi.json
- When the spec changes, check the guides for anything the change makes out of date
- Verify behavior against the spec before describing it. Pass upserts replace the whole pass; they do not merge.

## Adding a page

- Add the page to the navigation in `docs.json`
- Add a line for it in `llms.txt`

## Terminology

- **Template** - a reusable pass design. Use "template", not "design" or "class".
- **Pass** - an issued instance of a template. Use "pass", not "card" or "voucher", unless naming a pass type.
- **Account** - the organisation-level tenant that owns templates, passes, and API keys
- **Web viewer** - Passform's browser-based pass page, for users without a wallet app
- Write "Apple Wallet" and "Google Wallet" in full. Do not write "Google Pay".
- Pass types are offer, event, membership, and generic

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for field names, endpoints, file names, commands, and paths
- Use `YOUR_API_KEY` as the placeholder in examples, and `https://api.passform.io` as the base URL

## Content boundaries

- Document only what the public OpenAPI spec exposes. Do not document internal or admin endpoints.
- Do not include real API keys, account IDs, or customer data in examples
