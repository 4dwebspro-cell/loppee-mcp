# Loppee Discovery Agent Plugin

This metadata-only [Agent Plugins 1.0.0](https://agent-plugins.org) bundle
connects OpenClaw-compatible clients to Loppee's public, no-auth Streamable
HTTP MCP endpoint:

`https://loppee.com/mcp/discovery`

The endpoint exposes exactly five read-only named-business research tools:

- `lookup_business`
- `get_trust_card`
- `get_business_reviews`
- `explain_recommendation`
- `compare_businesses`

Agent Plugins 1.0.0 does not define a client-side tool allow-list in
`mcp.json`. The exact-five boundary is therefore enforced by the dedicated
server endpoint rather than duplicated as non-standard bundle metadata.

This bundle contains no skill, executable code, credentials, customer data,
owner tools, write tools, location input, or Back Office authority.

No `LICENSE` file is included. Public visibility does not grant an open-source
license.
