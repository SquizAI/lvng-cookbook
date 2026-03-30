<div align="center">

<img src="https://lvng.ai/logo.png" alt="LVNG" width="80" />

# LVNG Cookbook

### Ready-to-run API recipes in cURL, TypeScript, Python & Node.js

[![API Docs](https://img.shields.io/badge/API_Docs-lvng.ai%2Fdocs-6C5CE7?style=for-the-badge&logo=readthedocs&logoColor=white)](https://lvng.ai/docs/api)
[![OpenAPI](https://img.shields.io/badge/OpenAPI-3.0-85EA2D?style=for-the-badge&logo=openapiinitiative&logoColor=black)](https://lvng.ai/docs/openapi.json)
[![License: MIT](https://img.shields.io/badge/License-MIT-00D2FF?style=for-the-badge)](LICENSE)

---

```
  ┌─────────────────────────────────────────────────────────┐
  │                                                         │
  │   $ export LVNG_API_KEY="lvng_sk_live_..."              │
  │   $ curl api.lvng.ai/api/v2/workflows -H "x-api-key:   │
  │     $LVNG_API_KEY" | jq '.data[].name'                  │
  │                                                         │
  │   "Market Research Pipeline"                            │
  │   "Content Generator"                                   │
  │   "Weekly Report Automation"                            │
  │                                                         │
  └─────────────────────────────────────────────────────────┘
```

</div>

---

## Quick Start

```bash
# 1. Get an API key from https://app.lvng.ai/settings/developer

# 2. Set it
export LVNG_API_KEY="lvng_sk_live_..."

# 3. Run any example
./curl/list-workflows.sh
python python/create_agent.py
npx tsx typescript/search-knowledge.ts
```

## Install Packages

```bash
# MCP Server — connect Claude Code to your workspace
npm install -g https://api.lvng.ai/packages/lvng-mcp-server-1.0.0.tgz

# TypeScript SDK — programmatic access
npm install https://api.lvng.ai/packages/lvng-sdk-1.0.0.tgz
```

## Recipes

<table>
<thead>
<tr>
<th>Recipe</th>
<th><img src="https://img.shields.io/badge/-cURL-073551?logo=curl&logoColor=white" alt="cURL" /></th>
<th><img src="https://img.shields.io/badge/-TypeScript-3178C6?logo=typescript&logoColor=white" alt="TypeScript" /></th>
<th><img src="https://img.shields.io/badge/-Python-3776AB?logo=python&logoColor=white" alt="Python" /></th>
<th><img src="https://img.shields.io/badge/-Node.js-339933?logo=node.js&logoColor=white" alt="Node.js" /></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>List workflows</strong></td>
<td><a href="curl/list-workflows.sh">list-workflows.sh</a></td>
<td><a href="typescript/list-workflows.ts">list-workflows.ts</a></td>
<td><a href="python/list_workflows.py">list_workflows.py</a></td>
<td><a href="nodejs/list-workflows.js">list-workflows.js</a></td>
</tr>
<tr>
<td><strong>Execute workflow</strong></td>
<td><a href="curl/execute-workflow.sh">execute-workflow.sh</a></td>
<td><a href="typescript/execute-workflow.ts">execute-workflow.ts</a></td>
<td><a href="python/execute_workflow.py">execute_workflow.py</a></td>
<td><a href="nodejs/execute-workflow.js">execute-workflow.js</a></td>
</tr>
<tr>
<td><strong>Create agent</strong></td>
<td><a href="curl/create-agent.sh">create-agent.sh</a></td>
<td><a href="typescript/create-agent.ts">create-agent.ts</a></td>
<td><a href="python/create_agent.py">create_agent.py</a></td>
<td>-</td>
</tr>
<tr>
<td><strong>Message agent</strong></td>
<td><a href="curl/message-agent.sh">message-agent.sh</a></td>
<td><a href="typescript/message-agent.ts">message-agent.ts</a></td>
<td><a href="python/message_agent.py">message_agent.py</a></td>
<td>-</td>
</tr>
<tr>
<td><strong>Search knowledge</strong></td>
<td><a href="curl/search-knowledge.sh">search-knowledge.sh</a></td>
<td><a href="typescript/search-knowledge.ts">search-knowledge.ts</a></td>
<td><a href="python/search_knowledge.py">search_knowledge.py</a></td>
<td>-</td>
</tr>
<tr>
<td><strong>Stream chat (SSE)</strong></td>
<td><a href="curl/stream-chat.sh">stream-chat.sh</a></td>
<td><a href="typescript/stream-chat.ts">stream-chat.ts</a></td>
<td><a href="python/stream_chat.py">stream_chat.py</a></td>
<td>-</td>
</tr>
<tr>
<td><strong>Manage API keys</strong></td>
<td><a href="curl/api-keys.sh">api-keys.sh</a></td>
<td>-</td>
<td><a href="python/api_keys.py">api_keys.py</a></td>
<td>-</td>
</tr>
</tbody>
</table>

## Claude Code Integration

Connect Claude Code directly to your LVNG workspace with 21 MCP tools:

```json
{
  "mcpServers": {
    "lvng": {
      "command": "lvng-mcp-server",
      "env": {
        "LVNG_API_KEY": "lvng_sk_live_..."
      }
    }
  }
}
```

<details>
<summary><strong>Available MCP Tools (21)</strong></summary>

| Category | Tools |
|----------|-------|
| **Workflows** (9) | `list` `get` `create` `update` `delete` `execute` `get_run` `list_runs` `parse` |
| **Agents** (8) | `list` `get` `create` `update` `delete` `message` `start` `stop` |
| **Knowledge** (4) | `search` `ingest` `list_entities` `get_stats` |

</details>

## API Key Format

```
lvng_sk_live_7e8949d627f560d298f310ceeadb492c
|       |    |
|       |    +-- 32 random hex characters
|       +-- Environment (live / test)
+-- Prefix (identifies as LVNG per-user key)
```

Keys are SHA-256 hashed at rest. The raw key is shown **once** at creation time.

## Documentation

<div align="center">

[![API Reference](https://img.shields.io/badge/API_Reference-17_Resources-6C5CE7?style=flat-square)](https://lvng.ai/docs/api)
[![Cookbook](https://img.shields.io/badge/Cookbook-Web_Version-00D2FF?style=flat-square)](https://lvng.ai/docs/cookbook)
[![SDKs](https://img.shields.io/badge/SDKs_%26_Claude_Code-Setup_Guide-FF6B6B?style=flat-square)](https://lvng.ai/docs/sdks)
[![API Keys](https://img.shields.io/badge/API_Keys-Management-FFA502?style=flat-square)](https://lvng.ai/docs/api/api-keys)
[![OpenAPI](https://img.shields.io/badge/OpenAPI-JSON_Spec-85EA2D?style=flat-square)](https://lvng.ai/docs/openapi.json)

</div>

## License

MIT
