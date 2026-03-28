# Awesome AI Agent Tools

[![Dataset](https://img.shields.io/badge/tools-461-blue)](data/tools.json)
[![Stars Tracked](https://img.shields.io/badge/GitHub%20stars%20tracked-7.5M-yellow)](data/tools.json)
[![Updated](https://img.shields.io/badge/updated-daily-green)](https://agentoolrank.com)
[![License](https://img.shields.io/badge/license-MIT-brightgreen)](LICENSE)

A curated, data-driven dataset of **461 AI agent tools** ranked by GitHub activity. Updated daily via automated pipeline.

**Browse the full directory: [agentoolrank.com](https://agentoolrank.com)**

## What's Inside

- `data/tools.json` — Full dataset (461 tools with metrics, categories, descriptions)
- `data/tools.csv` — Same data in CSV format
- `data/categories.json` — 11 category definitions

## Top 20 by Activity Score

| Tool | Stars | Velocity | Pricing | Category |
|------|------:|----------|---------|----------|
| [n8n](https://agentoolrank.com/tool/n8n) | 181,354 | +15,113/mo | free | No-Code Builders |
| [AutoGPT](https://agentoolrank.com/tool/auto-gpt) | 182,873 | +15,239/mo | free | Agent Frameworks |
| [ollama](https://agentoolrank.com/tool/ollama) | 166,306 | +13,859/mo | open-source | LLM Runtime |
| [langflow](https://agentoolrank.com/tool/langflow) | 146,311 | +12,193/mo | open-source | No-Code Builders |
| [dify](https://agentoolrank.com/tool/dify) | 134,723 | +11,227/mo | free | No-Code Builders |
| [open-webui](https://agentoolrank.com/tool/open-webui) | 128,966 | +10,747/mo | free | Chat UI |
| [gemini-cli](https://agentoolrank.com/tool/gemini-cli) | 99,285 | +8,274/mo | open-source | CLI Tools |
| [llama.cpp](https://agentoolrank.com/tool/llama-cpp) | 99,588 | +8,299/mo | open-source | LLM Runtime |
| [browser-use](https://agentoolrank.com/tool/browser-use) | 84,716 | +7,060/mo | open-source | Browser Agents |
| [claude-code](https://agentoolrank.com/tool/claude-code) | 83,495 | +6,958/mo | free | Coding Agents |
| [vllm](https://agentoolrank.com/tool/vllm) | 74,524 | +6,210/mo | open-source | LLM Serving |
| [lobe-chat](https://agentoolrank.com/tool/lobe-chat) | 74,400 | +6,200/mo | free | Chat UI |
| [OpenHands](https://agentoolrank.com/tool/openhands) | 69,897 | +5,825/mo | free | Coding Agents |
| [codex](https://agentoolrank.com/tool/codex) | 67,989 | +5,666/mo | open-source | Coding Agents |
| [MinerU](https://agentoolrank.com/tool/mineru) | 57,387 | +4,782/mo | free | Document AI |
| [docling](https://agentoolrank.com/tool/docling) | 56,614 | +4,717/mo | open-source | Document AI |
| [firecrawl](https://agentoolrank.com/tool/firecrawl) | 99,207 | +8,267/mo | open-source | Browser Agents |
| [llama_index](https://agentoolrank.com/tool/llama-index) | 48,064 | +4,005/mo | open-source | RAG Framework |
| [langchain](https://agentoolrank.com/tool/langchain) | 131,299 | +10,943/mo | open-source | Agent Frameworks |
| [crewAI](https://agentoolrank.com/tool/crewai) | 30,120 | +2,510/mo | open-source | Agent Frameworks |

[View all 461 tools →](https://agentoolrank.com)

## Categories

| Category | Tools | Description |
|----------|------:|-------------|
| Agent Frameworks | 258 | Libraries and SDKs for building AI agents |
| Memory & Knowledge | 101 | Vector databases, RAG, knowledge graphs |
| Tool Integration | 85 | MCP servers, function calling, API connectors |
| Observability & Evaluation | 65 | Tracing, monitoring, eval frameworks |
| Enterprise Platforms | 51 | Enterprise-grade agent platforms |
| Voice Agents | 40 | Speech, TTS, telephony agents |
| No-Code Builders | 20 | Visual workflow builders for agents |
| Coding Agents | 19 | AI-powered coding assistants |
| Agent Protocols | 8 | Standards like MCP, A2A |
| Browser Agents | 7 | Web automation and scraping |
| Sandboxes | 3 | Isolated code execution environments |

## Ranking Methodology

Tools are ranked using a composite score based on:

- **Star velocity** (35%) — GitHub stars gained per month (30-day window)
- **Commit activity** (30%) — Commits in the last 90 days
- **Release frequency** (20%) — Releases in the last 6 months
- **Recency** (15%) — Exponential decay from last commit date

This favors **actively maintained, growing** projects over legacy repos with high star counts but low activity.

Full methodology: [agentoolrank.com](https://agentoolrank.com)

## Data Format

### tools.json

```json
{
  "id": "langchain",
  "name": "langchain",
  "tagline": "Build context-aware reasoning applications",
  "website": "https://langchain.com",
  "github": "https://github.com/langchain-ai/langchain",
  "categories": ["agent-frameworks", "memory-knowledge"],
  "stars": 131299,
  "star_velocity_30d": 10943,
  "last_commit": "2026-03-28T10:00:00Z",
  "releases_6m": 42,
  "pricing": "open-source",
  "score": 0.824,
  "rank_percentile": 99
}
```

## Usage

### Load in Python

```python
import json

with open("data/tools.json") as f:
    tools = json.load(f)

# Top 10 by stars
top = sorted(tools, key=lambda t: t["stars"] or 0, reverse=True)[:10]
for t in top:
    print(f"{t['name']}: {t['stars']:,} stars")
```

### Load in JavaScript/TypeScript

```typescript
import tools from "./data/tools.json";

const agentFrameworks = tools.filter((t) =>
  t.categories.includes("agent-frameworks")
);
console.log(`${agentFrameworks.length} agent frameworks`);
```

### Load in pandas

```python
import pandas as pd

df = pd.read_csv("data/tools.csv")
print(df.groupby("pricing")["stars"].sum())
```

## Updates

This dataset is updated daily via an automated GitHub Actions pipeline:

1. **Crawl** — Fetch latest metrics from GitHub GraphQL API
2. **Clean** — Remove non-agent tools, filter by relevance
3. **Rank** — Recompute activity scores and percentile ranks
4. **Export** — Generate fresh JSON/CSV files

## Contributing

Found a tool that should be listed? Open an issue with:
- GitHub repo URL
- Brief description of what it does
- Which category it belongs to

## License

MIT — free to use, modify, and distribute. Attribution appreciated.

Data sourced from public GitHub APIs. Tool descriptions generated by LLM based on public README content.

---

**Built by [AgenTool Rank](https://agentoolrank.com)** — The data-driven AI agent tools directory.
