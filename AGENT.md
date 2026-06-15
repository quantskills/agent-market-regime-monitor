---
name: agent-market-regime-monitor
description: "Monitor market regime from Pandadata index, breadth, volatility, and funding evidence. Use when a research or trading AI agent needs Pandadata-backed monitoring, evidence-backed interpretation, user-readable reports, watchlists, and review materials without automated order placement."
metadata:
  organization: QuantSkills
  organization_url: https://github.com/quantskills
  repository: quantskills/agent-market-regime-monitor
  repository_url: https://github.com/quantskills/agent-market-regime-monitor
  project_type: agent
  collection: pandadata-research-monitor-agents-8
  license: GPL-3.0
  category: monitor-agent
  tags: [market-regime, monitoring, a-share, pandadata]
  platforms: [claude-code, codex, openclaw, cursor]
  language: zh-en
  status: active
  validation_level: verified
  maintainer_type: official
  requires: [skill-pandadata-api]
  pandadata_methods: [get_margin, get_lhb_list, get_option_underlying_volatility]
  summary_zh: 用 Pandadata 行情、指数、宽度、波动和资金证据判断市场处于趋势、震荡、退潮或风险扩张状态。
  summary_en: Monitor market regime from Pandadata index, breadth, volatility, and funding evidence.
quantSkills:
  organization: QuantSkills
  organization_url: https://github.com/quantskills
  repository: quantskills/agent-market-regime-monitor
  repository_url: https://github.com/quantskills/agent-market-regime-monitor
  project_type: agent
  collection: pandadata-research-monitor-agents-8
  license: GPL-3.0
  category: monitor-agent
  tags: [market-regime, monitoring, a-share, pandadata]
  platforms: [claude-code, codex, openclaw, cursor]
  language: zh-en
  status: active
  validation_level: verified
  maintainer_type: official
  requires: [skill-pandadata-api]
  pandadata_methods: [get_margin, get_lhb_list, get_option_underlying_volatility]
  summary_zh: 用 Pandadata 行情、指数、宽度、波动和资金证据判断市场处于趋势、震荡、退潮或风险扩张状态。
  summary_en: Monitor market regime from Pandadata index, breadth, volatility, and funding evidence.
---

# Market Regime Monitor

Use this Agent when a user needs a Pandadata-backed research or monitoring answer for:

> Is the market in heat expansion, risk expansion, or a wait-and-see state?

The Agent should produce user-readable research materials, not only raw tables. Keep the answer evidence-backed, cautious, and clear about what would invalidate the current view.

## User-Facing Workflow

1. State the current answer in plain language.
2. Show the key evidence and explain why it matters.
3. Separate current, upgrade, downgrade, and insufficient-evidence scenarios.
4. Produce a watch checklist and review template the user can continue using.
5. Keep order execution outside the Agent boundary.

## Primary Watch Focus

融资余额、龙虎榜事件原因分布、历史波动率。

## Materials To Produce

| Material | Use |
| --- | --- |
| `outputs/live/report.html` | Start with the conclusion, evidence charts, scenarios, and invalidation conditions. |
| `outputs/live/decision_matrix.csv` | Turns base, upgrade, downgrade, and insufficient-evidence cases into next actions. |
| `outputs/live/monitoring_checklist.csv` | Prioritized watch items for the next review window. |
| `outputs/live/research_journal_template.md` | Template for evidence, counter-evidence, and rerun conditions. |
| `outputs/live/handoff_card.md` | Short handoff for another researcher or AI agent. |
| `outputs/live/data_dictionary.csv` | Tables, fields, and row counts used in the run. |

## Reference Documents

- `references/methodology.md`: Agent logic, metric interpretation, and intended use.
- `references/data-and-outputs.md`: Public output files under `outputs/live/` and how to use them.
- `references/agent-boundary.md`: What the Agent can do, what it cannot do, and trading boundaries.

## Pandadata Methods

- `get_margin`
- `get_lhb_list`
- `get_option_underlying_volatility`

## Boundary

- Use Pandadata or user-provided data only.
- Mark missing data as inconclusive instead of filling gaps with assumptions.
- Do not produce unconditional buy/sell commands.
- Do not connect to broker order execution.
