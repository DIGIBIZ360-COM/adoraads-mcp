# adoraads-mcp
The first MCP-native sponsored product ad network for beauty. Real-time RTB auction serves sponsored beauty products inside ChatGPT, Claude and every LLM. Skin-type targeting, IAB-compliant disclosure
markdown# adoraads.ai — Beauty LLM Ad Network

The first MCP-native sponsored product ad network for beauty.

## What it does

When a shopper asks ChatGPT or Claude "best serum for oily skin" —
adoraads.ai serves sponsored beauty products inside the AI's answer.
Not beside it. Inside it.

Real-time RTB auction · <100ms · IAB-compliant disclosure · 
Closed-loop ROAS

## MCP Endpoint
https://mcp.adoraads.ai/beauty

No authentication required for shopper tools.

## Tools

| Tool | Description |
|------|-------------|
| `sponsored_search` | RTB auction — returns sponsored beauty products matching skin type, concern, and budget |
| `brand_spotlight` | Sponsored brand content and hero product showcase |
| `routine_builder` | Sponsored products at each step of AM/PM skincare routine |
| `skin_match` | AI skin profile extraction from free text + matched sponsored products |
| `fire_billing_event` | CPM → CPE → CPR → CPA billing funnel |
| `get_shopper_prefs` | Shopper ad preference management |

## Quick Start — Claude Desktop

Add to `~/Library/Application Support/Claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "adoraads-beauty": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://mcp.adoraads.ai/beauty"
      ]
    }
  }
}
```

## Quick Start — test with curl

```bash
curl -X POST https://mcp.adoraads.ai/beauty \
  -H "Content-Type: application/json" \
  -d '{
    "jsonrpc": "2.0",
    "method": "tools/call",
    "params": {
      "name": "sponsored_search",
      "arguments": {
        "query": "best serum for oily skin under $40",
        "tenant_id": "tenant-test",
        "skin_type": "oily",
        "concern": "acne"
      }
    },
    "id": 1
  }'
```

## Billing Model

| Event | Trigger | Billing |
|-------|---------|---------|
| Context inclusion | Product enters AI context | CPM |
| Shortlist | AI shortlists product | CPE |
| Recommendation | AI recommends to shopper | CPR |
| Purchase | Shopper buys | CPA % |

## For Beauty Brands

50 founding brand spots — 3 months free.

→ [adoraads.ai](https://adoraads.ai)
→ hello@adoraads.ai
→ [linkedin.com/in/kalv](https://linkedin.com/in/kalv)

## Built by

Technology architect of a global luxury beauty retailer's 
retail media network. Duke MBA · BITS Pilani M.S. · 
35 years global executive experience.
[![smithery badge](https://smithery.ai/badge/kapilsbox/adoraads_ai)](https://smithery.ai/servers/kapilsbox/adoraads_ai)
https://smithery.ai/servers/kapilsbox/adoraads_ai
