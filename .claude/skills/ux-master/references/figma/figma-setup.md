# Figma setup

Everything here is about Figma's own MCP server. It was checked against Figma's
developer documentation in October 2026. Figma changes these details, so treat the linked
pages as the authority.

- Guide: https://developers.figma.com/docs/figma-mcp-server/
- Tools: https://developers.figma.com/docs/figma-mcp-server/tools-and-prompts/
- Limits: https://developers.figma.com/docs/figma-mcp-server/rate-limits-access/
- Setup guide on GitHub: https://github.com/figma/mcp-server-guide

## You may not need it

The audit works from an image too. If you are on a free Figma plan, or your AI tool is
not on Figma's list of supported clients, use the image route:

1. In Figma, select the frame.
2. In the right panel choose Export, set PNG at 2x, and export. Or copy the frame as PNG.
3. Give the file path to your agent, or paste the image into the chat, and ask for a UX
   audit of it.

The only difference is that sizes are estimated from the image instead of measured from
the file.

## Connect Figma's MCP server

There are two servers. The remote one needs no desktop app and reads a frame from its
link. The desktop one runs inside the Figma desktop app and can also read your current
selection.

### Claude Code

Recommended by Figma, installs the server settings and Figma's own skills:

```bash
claude plugin install figma@claude-plugins-official
```

Or add the remote server by hand:

```bash
claude mcp add --transport http figma https://mcp.figma.com/mcp
```

Add `--scope user` after `add` to make it available in every project. Then start a new
Claude Code session, run `/mcp`, choose `figma`, choose Authenticate and allow access in
the browser.

### Cursor, VS Code and other clients

Add a remote MCP server with the URL `https://mcp.figma.com/mcp` in your client's MCP
settings and sign in. For the Codex CLI the command is
`codex mcp add figma --url https://mcp.figma.com/mcp`. Figma's guide has the exact steps
for each client it supports.

Figma states that only clients listed in its MCP catalog can connect. If your tool is not
listed, use the image route.

## Give the agent a frame

- **Remote server:** in Figma, copy the link to the frame (select the frame, then use
  Copy link to selection) and paste it into your prompt. The link has to point at a
  specific frame or layer. The agent does not open the link. It reads the node id from it.
- **Desktop server:** select the frame in the Figma desktop app and say "audit my current
  Figma selection", or paste a link as above.

Example prompt: `Audit the UX of this frame: <link>`

## Limits

Figma counts each tool call that reads from a file.

| Seat | Starter | Professional | Organization | Enterprise |
|---|---|---|---|---|
| View or Collab | Up to 20 a month | Up to 20 a month | Up to 20 a month | Up to 20 a month |
| Dev or Full | Up to 20 a month | Up to 200 a day, 10 a minute | Up to 200 a day, 15 a minute | Up to 600 a day, 20 a minute |

Source: Figma's "Rate limits and access" page, read on 2026-10-07. On that page the
Starter plan gets 20 tool calls a month whatever the seat. Figma's GitHub setup guide,
read the same day, gives a lower figure for Starter plans and for View or Collab seats on
paid plans: up to 6 tool calls a month. The two pages disagree, so plan for the lower
number and check the limits page for the current one.

What this means for audits:

- One frame costs two calls by default (`get_screenshot` and `get_metadata`) and four at
  most.
- On a small monthly allowance that is a handful of frames a month at best. Use the image
  route for everyday reviews and keep the MCP calls for frames where exact measurements
  matter.
- `whoami` is listed by Figma as exempt from the limits. The agent uses it to see your
  plan and seat before spending calls.

## The four Figma tools the audit uses

| Tool | Returns |
|---|---|
| `get_screenshot` | An image of the frame |
| `get_metadata` | A sparse outline of the layers: ids, names, types, positions and sizes |
| `get_design_context` | A structured description of the frame, React and Tailwind by default |
| `get_variable_defs` | The variables and styles used: colors, spacing, typography |

The audit only reads. Figma's server also has tools that write to a file. The audit does
not call them.

## Troubleshooting

- **"Tool not found" or no Figma tools listed:** the server is not connected in this
  session. Check your client's MCP list, sign in again, or use the image route.
- **Permission error:** you can only read files your Figma account can open. Open the
  file in Figma first to confirm access.
- **Rate limit message:** the allowance is used up. Switch to the image route. Do not
  retry.
- **The agent audited the wrong thing:** the link pointed at the page or file, not the
  frame. Copy the link from the frame itself.
- **Sizes look wrong on the image route:** tell the agent the export scale ("this is a
  2x export of a 390 point wide frame").
