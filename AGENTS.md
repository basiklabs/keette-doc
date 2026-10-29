# Documentation project instructions

## About this project

- Keette Developers docs on [Mintlify](https://mintlify.com)
- Pages are MDX with YAML frontmatter
- Configuration lives in `docs.json`
- Brand: primary `#061F00`, accent `#A5E119`, font Uncut Sans (`/fonts/UncutSans-Variable.woff2`)
- Logo includes the Keette wordmark plus a **Developers** suffix

## Terminology

- Use **workspace** for a tenant account in product copy; `tenant` is fine in API field names
- Use **live** and **sandbox** (not “prod” / “dev”) for API environments
- Keys: `sk_live_…` / `sk_test_…`
- Event names: `event.<resource>` or `event.<resource>.<action>`

## Style preferences

- Active voice, second person ("you")
- Concise sentences — one idea per sentence
- Sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for paths, headers, and identifiers
- When a surface is not shipped yet, mark **Phase N** with a Note — do not invent request/response fields ahead of implementation

## Content boundaries

- **Guides** tab: concepts (auth, environments, webhooks, errors)
- **API reference** tab: list endpoints flat in `docs.json` as `"METHOD /path"` under a group with `"openapi": "openapi.yaml"`. Do **not** also list MDX pages for those same paths (duplicates), and do **not** omit the pages list (Mintlify then nests every OpenAPI tag as a collapse folder).
- Flat sidebar only: no collapse folders for endpoints
- OpenAPI `summary` is the sidebar label — keep it short (one line, no wrap). Group pages by resource (Balances, Transactions, Beneficiaries, FX…); within a group, shortest title first
- Do not document internal Payment/Ledger/admin operator APIs or session JWT app routes as public
- After each implementation phase, add the path to `openapi.yaml` and a `"METHOD /path"` entry in `docs.json` in the same change set

