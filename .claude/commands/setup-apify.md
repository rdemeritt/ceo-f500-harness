# /setup-apify — Apify MCP Setup

## Purpose

Configures the Apify MCP integration for this harness. Collects your Apify API token, saves it to the local `.env` file, and verifies the MCP configuration is in place.

## Usage

```
/setup-apify
```

---

## Workflow

### Step 1: Check Current State

Check whether Apify is already configured:

1. Run `echo $APIFY_TOKEN` — if a token is already set in the environment, report it (masked: show only last 4 characters) and ask the user if they want to update it.
2. Check whether `.env` exists in the project root and whether it contains `APIFY_TOKEN`.
3. Confirm `.mcp.json` exists at the project root.

Report findings before proceeding:

```
APIFY SETUP CHECK
─────────────────────────────────────────────
Environment variable APIFY_TOKEN:  [SET (ends in ...XXXX) | NOT SET]
.env file:                         [EXISTS | NOT FOUND]
APIFY_TOKEN in .env:               [PRESENT | MISSING]
.mcp.json config:                  [PRESENT | MISSING]
─────────────────────────────────────────────
```

If everything is already configured and the user does not want to update, exit with: "Apify MCP is already configured. Run `/mcp` in Claude Code to verify the server connection."

### Step 2: Collect the API Token

Use the `AskUserQuestion` tool to prompt:

> "Paste your Apify API token. Get it from the Apify Console → Integrations tab (https://console.apify.com/account/integrations). The token will be saved to your local .env file and never committed to git."

Accept the token as free-text input.

Validate the token format: Apify tokens begin with `apify_api_` followed by alphanumeric characters. If the input does not match this pattern, warn the user: "This doesn't look like an Apify API token (expected format: apify_api_...). Double-check the value and try again." Do not proceed with an invalid-format token unless the user explicitly confirms they want to continue.

### Step 3: Save to .env

Write `APIFY_TOKEN=<token>` to the `.env` file in the project root.

- If `.env` does not exist: create it with the token as the first entry.
- If `.env` exists but does not contain `APIFY_TOKEN`: append the line.
- If `.env` exists and already contains `APIFY_TOKEN`: replace the existing line.

Never overwrite other entries in `.env`.

After writing, confirm the file was updated by reading it back and verifying the token is present (display masked: `APIFY_TOKEN=apify_api_...XXXX`).

### Step 4: Verify .mcp.json

Confirm `.mcp.json` exists at the project root and contains the `apify` server entry. If it is missing or malformed, display:

```
WARNING: .mcp.json is missing or does not contain the Apify server configuration.
The MCP server will not load. Run the following to restore it:

  git checkout .mcp.json

Or refer to .claude/SETUP.md Step 5 for the full configuration.
```

If `.mcp.json` is present and correct, confirm: ".mcp.json verified — Apify server entry is present."

### Step 5: Confirm and Next Steps

Output the final setup confirmation:

```
APIFY MCP SETUP COMPLETE
════════════════════════════════════════════════
✓ APIFY_TOKEN saved to .env
✓ .env is listed in .gitignore (token will not be committed)
✓ .mcp.json verified

NEXT STEPS
────────────────────────────────────────────────
1. Load the token into your current shell session:

     export APIFY_TOKEN=$(grep APIFY_TOKEN .env | cut -d= -f2)

   Or start a new shell session — Claude Code will pick up the
   token from .env automatically on next launch.

2. Verify the MCP server is connected:
   Run /mcp inside Claude Code. You should see "apify" listed
   as a connected server with 7 pinned actors available.

3. Run your first research request:
   /research [your topic]

────────────────────────────────────────────────
Pinned actors ready:
  • apify/rag-web-browser          Web search + page summarization
  • apify/google-search-scraper    Structured SERP data
  • apify/website-content-crawler  Full site analysis
  • apify/cheerio-scraper          Fast static HTML extraction
  • get-leads/linkedin-scraper     Company and executive profiles
  • scraped/edgar-filing-data-...  SEC EDGAR filings
  • dorcy/advanced-news-scraper    News across 4,500+ sources
════════════════════════════════════════════════
```

---

## Security Notes

- The `.env` file is listed in `.gitignore` and will never be committed to source control.
- The token is never logged, printed in full, or included in any agent output.
- If you believe your token has been compromised, rotate it immediately at https://console.apify.com/account/integrations and re-run `/setup-apify`.
- The Apify token grants access to your Apify account and will incur charges when actors are run. Treat it like a password.

---

_Command Version: 1.0.0 | Fortune 500 AI Business Operating System_
