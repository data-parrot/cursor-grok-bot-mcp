<p align="center">
  <img src="assets/data-parrot-icon.svg" alt="Data Parrot" width="112">
</p>

# Data Parrot MCP Server for Cursor and Grok Bot

Ask Cursor or Grok Bot about your HubSpot forecast, pipeline, deals, sales activity, customer health, and win/loss using analysis Data Parrot has already completed.

[Website](https://dataparrot.ai) · [MCP documentation](https://dataparrot.ai/docs/mcp) · [Connection guide](https://dataparrot.ai/docs/mcp/connect) · [Prompt library](https://dataparrot.ai/docs/mcp/prompts)

## What is the Data Parrot MCP server?

[Data Parrot](https://dataparrot.ai) is an AI revenue intelligence platform for CEOs, CROs, and revenue leaders using HubSpot. It monitors every deal, pipeline movement, and customer interaction so revenue teams can trust the forecast, catch slippage early, and focus the team where it matters.

The Data Parrot MCP server brings that analysis into AI tools that support the [Model Context Protocol](https://modelcontextprotocol.io). Instead of starting with raw CRM records and rebuilding the analysis in every conversation, your AI tool can use Data Parrot's deal health, forecast risk, pipeline movement, customer health, sales activity, and win/loss analysis.

This repository contains the Agent Plugin manifest used by Cursor and Grok Bot. The MCP server itself is hosted by Data Parrot at `https://api-v3.dataparrot.ai/api/v3/data-parrot/mcp`. There is no local server to run or separate package to maintain.

## Why use Data Parrot with HubSpot?

Your CRM has the data. Data Parrot has already analyzed how your company sells and what is happening across the sales organization, from individual deals and customers to the forecast and the reasons behind wins and losses.

Data Parrot uses HubSpot CRM fields alongside emails, calls, meetings, notes, property changes, transcripts, and buyer engagement when that information is available. Your CRM does not have to be perfect before you can ask a useful sales question.

Every conversation starts with analysis Data Parrot has already done. You can ask what changed, what is at risk, and where the team needs to focus without first explaining your pipeline or asking the model to reconstruct deal history record by record.

## What can Data Parrot do through MCP?

### Sales forecasting

Build a realistic forecast from closed-won revenue, the remaining pipeline, deal-level risk, best-case upside, and the deals most likely to move the number. You can ask where the business will land this month or quarter and inspect the deals behind the answer.

### Deal health and forecast risk

Review purchase intent, deal progress, stage confidence, close-date confidence, buyer engagement, and forecast risk. Find high-value deals that are stuck, going quiet, slipping, or showing stronger intent than their stage suggests.

### Pipeline analysis

See how the pipeline changed over a period and which deals caused the movement. Data Parrot can help explain pipeline growth, shrinkage, pushed close dates, stage changes, and the deals that need attention now.

### Sales activity and coaching

Use activity and deal evidence to identify where reps need coaching and which deals belong in the next review. This gives leaders a concrete place to start instead of another generic activity summary.

### Customer health

Find high-value customers that need attention and review the supporting account activity. This helps teams spot customer risk before the next renewal or executive review.

### Win/loss analysis

Understand why deals are won and lost using the available CRM and customer activity. Compare reasons across deals, segments, owners, competitors, and time periods without manually reading every record.

## Questions you can ask

Start with questions your revenue team already asks:

- "Where will we land this month? Include closed-won revenue, a realistic remaining forecast, best case, and the deals that could move the number."
- "Which deals put this month's forecast at risk?"
- "Which high-value deals have strong buyer intent but are stuck or going quiet?"
- "What grew or shrank our pipeline this quarter, and which deals caused the change?"
- "Which reps need coaching right now, and which deals should we review with them?"
- "Which high-value customers should we be worried about?"
- "Why are we winning and losing?"

See the [Data Parrot prompt library](https://dataparrot.ai/docs/mcp/prompts) for more examples covering forecasts, open deals, pipeline movement, sales activity, customer health, and win/loss analysis.

## Use the analysis in your existing workflow

The answer does not have to stay in chat. When your AI tool has access to the right file or productivity apps, it can use Data Parrot's analysis to help create a forecast deck, prepare a deal review, update a planning document, or build a working spreadsheet.

Data Parrot supplies the revenue analysis and supporting details. Cursor, Grok Bot, or another connected AI tool handles the document or workflow in the apps you have authorized.

## How it works

1. Data Parrot connects to HubSpot and analyzes deals, pipeline movement, sales activity, customer accounts, and won and lost business.
2. You add the Data Parrot plugin to Cursor or Grok Bot.
3. Data Parrot asks you to sign in through your browser and choose the account you want to use.
4. Your AI tool calls the hosted Data Parrot MCP server when a question needs revenue analysis or supporting details.

## Install and test in Cursor

The public Cursor Marketplace listing is not live yet. Until it is approved, you can test the plugin locally if you have access to this repository.

1. Clone this repository.
2. Copy it to `~/.cursor/plugins/local/data-parrot`, or symlink the repository to that location:

   ```bash
   ln -s /path/to/cursor-grok-bot-mcp ~/.cursor/plugins/local/data-parrot
   ```

3. Restart Cursor or run `Developer: Reload Window`.
4. Open **Customize** and confirm that the Data Parrot MCP server appears.
5. Start a conversation, ask a Data Parrot question, and complete browser sign-in when prompted.

Cursor documents this process under [Test plugins locally](https://cursor.com/docs/plugins). Once the Marketplace listing is approved, installation will move to the standard one-click flow in Cursor.

## Install in Grok Bot

Grok Bot installs plugins from the Cursor Marketplace. After the Data Parrot listing is approved:

1. Open **Plugins** in the Grok Bot sidebar.
2. Search for **Data Parrot** and add the plugin.
3. Complete Data Parrot sign-in in your browser.
4. Confirm that Data Parrot appears under **Installed**, then ask a forecast, pipeline, deal, customer health, or win/loss question.

If you use Grok Bot through a Cursor team, your team admin controls which Marketplace plugins are available. See Cursor's [Grok Bot plugin guide](https://cursor.com/help/grok-bot/connect-plugins) for the current installation flow.

## Data Parrot MCP vs. HubSpot MCP

Data Parrot MCP and HubSpot MCP solve different jobs and can be used side by side.

| | Data Parrot MCP | HubSpot MCP |
| --- | --- | --- |
| Primary job | Answer revenue questions using analysis Data Parrot has already produced | Give an AI tool access to supported HubSpot CRM records and activities |
| Best for | Forecasting, deal risk, pipeline movement, coaching, customer health, and win/loss analysis | Looking up CRM data and taking supported actions in HubSpot |
| Information returned | Data Parrot analysis with supporting HubSpot details | Supported HubSpot records, activities, and account information |
| Revenue data access | Read-only | Read and write access depends on the supported object and configured scopes |

Use [HubSpot's MCP server documentation](https://developers.hubspot.com/ai-tools/mcp) for direct CRM access. Use Data Parrot when the question requires the sales analysis behind the records.

## Plans, access, and data permissions

You need a connected HubSpot account and a Data Parrot Pro or Max workspace. MCP access is included with those plans at no additional Data Parrot charge.

Access to revenue data through the Data Parrot MCP server is read-only. The server cannot edit HubSpot or Data Parrot revenue records. Browser sign-in, workspace selection, and access requests are part of connection setup and do not change revenue records.

Review [Data access, security, and permissions](https://dataparrot.ai/docs/mcp/faq) before connecting Data Parrot to an AI tool.

## Other supported AI tools

The same hosted Data Parrot MCP server can also connect to ChatGPT, the Codex app and CLI, Claude.ai, Claude Desktop, Claude Code, Grok.com, Grok CLI, and other clients that support remote MCP servers and browser OAuth.

Start with the [connection guide](https://dataparrot.ai/docs/mcp/connect) and choose your client.

## Documentation and support

- [Data Parrot MCP overview](https://dataparrot.ai/docs/mcp)
- [Connect an AI tool](https://dataparrot.ai/docs/mcp/connect)
- [Questions and prompts to try](https://dataparrot.ai/docs/mcp/prompts)
- [Data access, security, and permissions](https://dataparrot.ai/docs/mcp/faq)
- [Contact Data Parrot](https://dataparrot.ai/contact)

## License

This Agent Plugin package is available under the [MIT License](LICENSE).
