# Passform docs

Source for [docs.passform.io](https://docs.passform.io), the public documentation for the Passform API. Built with [Mintlify](https://mintlify.com).

## Structure

| Path | Purpose |
|------|---------|
| `index.mdx`, `quickstart.mdx` | Getting started pages |
| `guides/` | Guides and integration pages |
| `api-reference/openapi.json` | OpenAPI spec the API reference tab is generated from |
| `api-reference/introduction.mdx` | API reference landing page |
| `docs.json` | Site configuration and navigation |
| `llms.txt` | Page index for AI tools - update it when you add or rename a page |

## Development

Install the [Mintlify CLI](https://www.npmjs.com/package/mint) and run the preview from the repo root:

```bash
npm i -g mint
mint dev
```

View the local preview at `http://localhost:3000`. Run `mint broken-links` to check links before opening a pull request.

## Syncing the API reference

The API reference is generated from `api-reference/openapi.json`, a copy of the spec served by the API. Refresh it whenever the API changes:

```bash
npm run sync-openapi:prod   # from https://api.passform.io/openapi.json
npm run sync-openapi        # from a local Firebase emulator
```

Sync from production unless you are documenting a change that has not been deployed yet.

## Publishing

Changes are deployed automatically when they are merged to `main`.
