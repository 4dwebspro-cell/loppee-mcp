# Loppee MCP

Public metadata for Loppee's narrow, no-auth MCP discovery surface.

## Connect

- MCP URL: `https://loppee.com/mcp/discovery`
- Transport: Streamable HTTP
- Authentication: none
- Registry identity: `com.loppee/loppee`

Configure the URL above as a remote HTTP MCP server in a compatible client.
This repository does not contain credentials and does not require an API key.

## Public tool boundary

The endpoint exposes exactly five read-only named-business research tools:

| Tool | Purpose |
| --- | --- |
| `lookup_business` | Find pay-independent exact or genuine-prefix matches for a named business. |
| `get_trust_card` | Read the published Trust Card for an identified Loppee business. |
| `get_business_reviews` | Read paginated public reviews and their published disclosures. |
| `explain_recommendation` | Read the published recommendation basis for an identified business. |
| `compare_businesses` | Compare two to twenty identified published Loppee businesses. |

Every tool is declared read-only, non-destructive, and closed-world. This
surface exposes no category discovery, address or location input, pricing,
checkout, customer account, business-owner, write, or Back Office authority.

## Privacy and neutrality

- The tool schemas accept no address, city, state, ZIP, coordinates, location
  handoff, or device-location input.
- The endpoint returns no private customer or owner data.
- Payment does not change lookup, comparison, verification, reviews, evidence,
  or recommendation explanation on this surface.
- Missing or unresolved records must remain unresolved rather than fabricated.

Loppee Personal, authenticated consumer MCP, Loppee Business, and Back Office
are separate products with different authorization boundaries. They are not
published through this repository.

## Registry metadata

`server.json` prepares version `0.1.2` of the existing
`com.loppee/loppee` Official MCP Registry listing. Registry versions are
immutable after publication. The file is a candidate until the official
Registry reports version `0.1.2` as active.

## Verification

Before any Registry release, Loppee validates `server.json` with the official
`mcp-publisher`, calls the live MCP `tools/list` method, verifies the exact
five-tool catalog and annotations, and exercises the read-only tools. Those
release checks run from Loppee's private product repository and CI; no backend
source, credentials, workflows, or operational runbooks are published here.

## Links

- Website: https://loppee.com
- Agent information: https://loppee.com/agents
- Privacy: https://loppee.com/privacy
- Terms: https://loppee.com/terms
- Support: https://loppee.com/support

## Source and license

This public repository intentionally contains metadata and documentation only.
It does not contain the Loppee backend, private application source, scripts,
workflows, secrets, credentials, or customer data.

No `LICENSE` file is included. Public visibility does not grant an open-source
license.
