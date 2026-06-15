# 市场状态盯盘 Agent

这是 QuantSkills 组织的 Pandadata 研究/盯盘 Agent：`agent-market-regime-monitor`。

它面向研究员、交易者和使用 AI Agent 做市场复盘的用户。它不会自动下单，也不会输出无条件买卖指令；它的作用是把真实市场数据整理成你可以阅读、复盘和继续跟踪的研究材料。

## 它帮你回答什么

当前市场环境是热度扩张、风险扩张，还是需要先观望？

## 你什么时候会用它

- 你想先判断一个市场状态、风险状态或研究线索是否值得继续看。
- 你需要把 Pandadata 数据转成图文报告，而不是只看原始表格。
- 你需要给自己或团队留下一份可复盘的观察清单。
- 你希望把结果交给另一个研究员或 AI Agent 继续分析。

## 本 Agent 的核心观察焦点

融资余额、龙虎榜事件原因分布、历史波动率。

## 如何阅读输出

本仓库已经附带一份 Pandadata live 示例输出，位于 `outputs/live/`。

1. 先打开 `outputs/live/report.html`，读核心结论和适合回答的问题。
2. 再看三张证据图，确认主判断、辅助证据和 scorecard 指标是否一致。
3. 用 `outputs/live/decision_matrix.csv` 判断当前是延续、升级、降级还是证据不足。
4. 用 `outputs/live/monitoring_checklist.csv` 建立下一轮盯盘清单。
5. 用 `outputs/live/research_journal_template.md` 写复盘，用 `outputs/live/handoff_card.md` 做交接。

## 你会得到的材料

| 材料 | 怎么用 |
| --- | --- |
| `outputs/live/report.html` | 先看结论、证据图、情景推演和反证条件。 |
| `outputs/live/decision_matrix.csv` | 把当前、升级、降级、证据不足四类情景转成后续动作。 |
| `outputs/live/monitoring_checklist.csv` | 下一轮盯盘的优先级清单。 |
| `outputs/live/research_journal_template.md` | 记录支持证据、反证证据和下次重跑条件。 |
| `outputs/live/handoff_card.md` | 把本次判断交给另一个研究员或 AI Agent。 |
| `outputs/live/data_dictionary.csv` | 查看使用的数据表、字段和行数。 |

## 使用的数据

- `get_margin`
- `get_lhb_list`
- `get_option_underlying_volatility`

## 升级与降级线索

- 升级观察：融资余额、事件热度和承接质量继续同向改善。
- 降级观察：热度仍高但融资余额回落、波动率升高或承接转弱。

## 边界

这是研究和盯盘 Agent，不是自动交易系统。它不接券商接口，不执行订单，不替用户做最终交易决定。用户需要结合自己的策略、风险预算和执行系统使用这些材料。

## License

GNU General Public License v3.0。详见 [LICENSE](LICENSE)。
