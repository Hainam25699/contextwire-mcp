# ContextWire MCP Server

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![MCP](https://img.shields.io/badge/MCP-Compatible-green.svg)](https://modelcontextprotocol.io/)
[![SimpleQA](https://img.shields.io/badge/SimpleQA-94.3%25-brightgreen.svg)](https://contextwire.dev/compare.html)
[![Free Tier](https://img.shields.io/badge/Free_Tier-1000_queries%2Fmo-blue.svg)](https://contextwire.dev)

A [Model Context Protocol](https://modelcontextprotocol.io/) server that gives AI agents access to web search across **105 engines**, academic research, content extraction, and more.

**94.3% accuracy on [SimpleQA](https://openai.com/index/introducing-simpleqa/) benchmark.**

## Quick Setup

Add to your MCP client config (Claude Desktop, Claude Code, Cursor, etc.):

```json
{
  "mcpServers": {
    "contextwire": {
      "url": "https://contextwire.dev/mcp"
    }
  }
}
```

No local server needed — it's a hosted MCP endpoint.

## Tools

| Tool | Description |
|------|-------------|
|  | Ask a factual question → synthesized answer with sources |
|  | Web search across 105 engines with 14 search profiles |
|  | Extract clean text/markdown from any URL |
|  | Search academic papers (arXiv, PubMed, Semantic Scholar, etc.) |
|  | Run multiple searches in parallel |

## Search Profiles

| Profile | Engines | Best for |
|---------|---------|----------|
|  | Google, Bing, DDG, Wikipedia | General search |
|  | Google News, Bing News | Current events |
|  | arXiv, PubMed, Semantic Scholar | Research papers |
|  | GitHub, StackOverflow | Programming |
|  | Hacker News, Lobsters, Reddit | Developer news |
|  | Yahoo Finance, market data | Financial data |
|  | GitHub, GitLab | Code repositories |
|  | npm, PyPI, crates.io | Package search |
|  | CVE databases | Security advisories |
|  | Reddit, Twitter | Social media |
|  | Wikipedia, Wiktionary | Reference material |
|  | Google Images, Bing Images | Image search |
|  | YouTube, Vimeo | Video search |
|  | All 105 engines | Maximum coverage |

## API Examples

### Ask a question
```bash
curl "https://contextwire.dev/api/ask" \
  -H "Authorization: Bearer YOUR_KEY" \
  -d '{"q": "What is the current price of Bitcoin?"}'
```

### Search with profiles
```bash
curl "https://contextwire.dev/api/search?q=rust+async+tutorial&profile=code" \
  -H "Authorization: Bearer YOUR_KEY"
```

### Extract a page
```bash
curl "https://contextwire.dev/api/extract?url=https://example.com&format=markdown" \
  -H "Authorization: Bearer YOUR_KEY"
```

## Free Tier

- **1,000 queries/month** — no credit card required
- **BYOK supported** — bring your own LLM key to save credits
- **/bin/bash LLM cost** — default model is free via OpenRouter

Get your API key at **[contextwire.dev](https://contextwire.dev)**.

## Node.js SDK

```bash
npm install @contextwire/sdk
```

```js
import { ContextWire } from '@contextwire/sdk';

const cw = new ContextWire('YOUR_API_KEY');
const answer = await cw.ask('Who invented the transistor?');
console.log(answer.answer);
```

SDK repo: [github.com/keptlive/contextwire-sdk](https://github.com/keptlive/contextwire-sdk)

## Links

- **Website**: [contextwire.dev](https://contextwire.dev)
- **API Docs**: [contextwire.dev/docs](https://contextwire.dev/docs.html)
- **Quickstart**: [contextwire.dev/quickstart](https://contextwire.dev/quickstart.html)
- **Playground**: [contextwire.dev/playground](https://contextwire.dev/playground.html)
- **Compare**: [contextwire.dev/compare](https://contextwire.dev/compare.html)
- **Status**: [contextwire.dev/status](https://contextwire.dev/status.html)

## License

MIT
