# Data Parrot

Data Parrot connects to HubSpot and learns how your company sells. Its MCP server brings deal health, sales forecasting, pipeline analysis, customer health, and win/loss analysis into your AI tools.

See which deals put your forecast at risk, what changed in your pipeline, which customers need attention, where reps need coaching, and why deals are won or lost, directly in the AI tools your team already uses.

Data Parrot brings its analysis and supporting details into your AI tools, so you can answer sales questions, create documents, and run workflows without explaining your business or rebuilding the analysis first.

## Install (Cursor)

1. Install this plugin from the Cursor Marketplace (or load it locally).
2. Sign in to Data Parrot in the browser when the host prompts. You need a HubSpot account and a Data Parrot Pro or Max workspace.
3. Ask forecast, pipeline, deal, customer-health, or win/loss questions.

The MCP server is hosted at `https://api-v3.dataparrot.ai/api/v3/data-parrot/mcp` (Streamable HTTP, OAuth). This package does not run a second server.

Revenue data access is read-only. Data Parrot cannot edit HubSpot or Data Parrot revenue records. Review [data access and permissions](https://dataparrot.ai/docs/mcp/faq) before connecting.

## Docs

- https://dataparrot.ai/docs/mcp
- https://dataparrot.ai/docs/mcp/connect
- https://dataparrot.ai/docs/mcp/connect/cursor-grok-bot
- https://dataparrot.ai/docs/mcp/prompts
