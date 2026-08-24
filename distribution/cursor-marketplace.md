# Cursor direct install and Marketplace packet

Status: candidate only. The deeplink has not been accepted on a user's machine,
and the plugin has not been submitted to or published in the Cursor Marketplace.

## Direct install

Decoded server configuration:

```json
{
  "url": "https://loppee.com/mcp/discovery"
}
```

Base64 encoding:

```text
eyJ1cmwiOiJodHRwczovL2xvcHBlZS5jb20vbWNwL2Rpc2NvdmVyeSJ9
```

Install link:

```text
cursor://anysphere.cursor-deeplink/mcp/install?name=loppee&config=eyJ1cmwiOiJodHRwczovL2xvcHBlZS5jb20vbWNwL2Rpc2NvdmVyeSJ9
```

The link only prefills an MCP installation. Cursor must show the decoded config
and the user must confirm. It contains no executable command, package, account,
header, credential, variable, or key.

## Local plugin preflight

The repository uses Cursor's documented plugin layout:

```text
.cursor-plugin/plugin.json
mcp.json
README.md
```

Before Marketplace submission:

1. Copy or symlink the repository to `~/.cursor/plugins/local/loppee`.
2. Restart Cursor or run `Developer: Reload Window`.
3. Confirm the `loppee` plugin and its root `mcp.json` are discovered.
4. Confirm the decoded remote is exactly
   `https://loppee.com/mcp/discovery`, with no header or variable prompt.
5. Confirm `tools/list` contains exactly the canonical five read-only tools and
   that no resource or prompt is advertised.
6. Confirm schemas and results contain no caller-location authority, signed
   media token, internal action array, account/owner/admin authority, or secret.
7. Run the five canaries from `claude-connectors-directory.md`; the runtime
   contract is client-neutral.
8. Record the Cursor version, operating system, UTC time, and result.

## Official Marketplace prerequisites

- Public Git repository containing the plugin.
- An approved open-source license for the repository. Loppee intentionally has
  no `LICENSE` today, so Marketplace submission is blocked until the owner
  selects and approves a license. The direct install link is unaffected.
- Valid `.cursor-plugin/plugin.json` at the repository root's documented
  manifest location.
- Unique lowercase kebab-case plugin name.
- Clear description and README setup/usage documentation.
- Valid relative component paths; no absolute filesystem paths or `..`.
- All `${VAR}` placeholders declared in the manifest's variables schema. Loppee
  has no variables or placeholders.
- Local Cursor test completed.
- Optional logo committed to the public repository and referenced by relative
  path. The candidate intentionally omits `logo` until that asset is added.
- Repository submitted at `https://cursor.com/marketplace/publish` and accepted
  under Cursor's current publisher terms.

Submitting the repository is an external action. Obtain immediate owner
approval before submission; a working deeplink does not prove Marketplace
review, listing, installation, or publication.

The public Marketplace search did not surface a Loppee plugin during this
preflight, but uniqueness is not proven until Cursor accepts the `loppee` name
in the signed-in submission flow.

Current official references:

- https://cursor.com/docs/mcp/install-links
- https://cursor.com/docs/mcp
- https://cursor.com/docs/plugins
- https://cursor.com/docs/reference/plugins
