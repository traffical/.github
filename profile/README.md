<p align="center">
  <a href="https://traffical.io">
    <img src="https://avatars.githubusercontent.com/u/48626943?s=120" alt="Traffical" width="96" />
  </a>
</p>

<h1 align="center">Traffical</h1>

<p align="center">
  Experimentation, feature management, and adaptive optimization — built on one primitive: the <strong>typed parameter</strong>.
</p>

<p align="center">
  <a href="https://traffical.io">Website</a> ·
  <a href="https://docs.traffical.io">Docs</a> ·
  <a href="https://docs.traffical.io/quickstart">Quickstart</a> ·
  <a href="https://app.traffical.io">Dashboard</a>
</p>

---

Building got cheap — knowing what each change did, did not. Traffical keeps three things in lockstep: how fast you ship, how fast you contain changes that hurt, and how fast you produce evidence you trust.

Instead of boolean feature flags, Traffical starts from the **parameter**: a typed, versioned value with a default. A/B tests, gradual rollouts, feature flags, and contextual bandits are all policies on top of the same primitive — same SDKs, same layers, same dashboard.

## How it works

- **Local resolution** — SDKs fetch a config bundle and resolve in-process, in sub-milliseconds. No per-request API calls; works offline and at the edge.
- **Layered experimentation** — mutual exclusivity within a layer, orthogonal bucketing across layers. Run dozens of concurrent experiments without contamination.
- **Warehouse-native metrics** — define metrics as SQL against Postgres, BigQuery, Snowflake, Databricks, or ClickHouse. No second event pipeline required.
- **Adaptive optimization** — Thompson Sampling, UCB1, Epsilon-Greedy, and linear contextual bandits that personalize per user.
- **Honest statistics** — sequential (anytime-valid) testing, CUPED variance reduction, and deliberately conservative impact estimates.
- **Governance built in** — changes state intent before carrying traffic, risk-scaled approval gates, and a decision record for every transition. Agents act through the [MCP server](https://docs.traffical.io/tools/mcp-server) under the same gates, not around them.

## Repositories

| Repository | What it is |
|---|---|
| [js-sdk](https://github.com/traffical/js-sdk) | JavaScript/TypeScript SDKs — Node, browser, React, Svelte, React Native |
| [php-sdk](https://github.com/traffical/php-sdk) | PHP SDK for server-side PHP 8.1+ |
| [sdk-spec](https://github.com/traffical/sdk-spec) | Language-agnostic SDK spec — every SDK buckets identically |
| [cli](https://github.com/traffical/cli) | Config-as-code: parameters, events, and metrics in version-controlled YAML |
| [skills](https://github.com/traffical/skills) | Agent skills, so coding agents can run experiments under governance |
| [docs](https://github.com/traffical/docs) | Source for [docs.traffical.io](https://docs.traffical.io) |

SDKs for Python and Swift (iOS/macOS/tvOS/watchOS) are documented at [docs.traffical.io/sdks](https://docs.traffical.io/sdks/overview).

## Get started

```bash
npm install @traffical/node
```

```typescript
const params = traffical.getParams({
  context: { userId: "user_789" },
  defaults: {
    "checkout.headline": "Complete your order",
    "pricing.discount_pct": 0,
  },
});
```

Any type, any number of variants, resolved locally. Follow the [quickstart](https://docs.traffical.io/quickstart) to run your first experiment in under five minutes.
