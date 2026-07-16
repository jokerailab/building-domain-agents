# 如何做「专用领域 Agent」——一套实战方法论

> 通用 Agent 和 Coding Agent 无法覆盖各行各业的专业场景——它们不够懂业务。
> 这个时代，专用领域的 Agent 会越来越多。做它 = **通用 Agent 架构 × 专业业务能力**。

这套方法论，把做一个**真实的**专用领域 Agent 的完整过程——从架构、模型、工具、记忆，到业务建模、数据真实性、工程运维、产品化——一章一章拆开写下来。**不是教程，是一个产品创作者的实战复盘 + 一套可复制的方法。**

**案例载体**：**野行 Y**，一个自驾行程规划 Agent（后来长成自驾约伴社交平台）。架构对标 Claude Code，业务是旅行（机票 / 住宿 / 租车 / 路线 / 时间）。

- 📖 **在线阅读**（推荐，有侧栏目录 + 逐章导航）：<https://travel.qiaokezhizao.top/methodology>
- 🧭 **野行 Y 计划 · 路线图**（作者亲手做的自驾路线）：<https://qiaokezhizao.top/yplan/>

---

## 目录

**写在前面**

- [写在前面的话](chapters/00-00-preface.md)

**开篇**

- [开篇 · 为什么要做「专用 Agent」](chapters/00-00-intro.md)

**一 · Agent 架构地基**

- [Agentic Loop：模型驱动的循环，不是固定流水线](chapters/01-01-agentic-loop.md)
- [工具即能力边界：自文档化、参数、返回结构](chapters/01-02-tools-as-boundary.md)
- [上下文工程：窗口里放什么、不放什么、怎么压](chapters/01-03-context-engineering.md)
- [记忆系统：让 Agent 记得你，又不记岔](chapters/01-04-memory.md)
- [子 Agent 与并行：把脏活和核对交出去](chapters/01-05-subagents.md)
- [持续交互：什么时候停下来，怎么把话接上](chapters/01-06-interaction.md)

**二 · 模型层**

- [模型分层：不同步骤用不同的脑子](chapters/02-01-model-tiering.md)
- [网关与 fallback 链：挂了自动换，还得连得上](chapters/02-02-gateway.md)
- [并发闸门：把「无感降级」换成「看得见的排队」](chapters/02-03-concurrency.md)
- [弱模型护栏：让最坏情况也体面、可恢复](chapters/02-04-weak-model-guards.md)

**三 · 为专业领域设计工具**

- [从业务动作到工具：旅行到底需要哪些工具](chapters/03-01-action-to-tool.md)
- [工具设计模式：搜索、估算、推荐、核实、选择](chapters/03-02-tool-patterns.md)
- [真实性优先：宁可少给，绝不编造](chapters/03-03-truthfulness.md)
- [数据护城河：自建一个「判断层」](chapters/03-04-data-moat.md)

**四 · 业务领域建模**

- [用户到底要什么](chapters/04-01-what-users-want.md)
- [目的地与路线：地理不讲情面](chapters/04-02-route-geo.md)
- [机票：在没有完美数据源时，做出诚实可用的能力](chapters/04-03-flights.md)
- [住宿与租车：判断在库、交易在链、境内外两套世界](chapters/04-04-stay-car.md)
- [时间与预算：把零件编排成一份可行的行程](chapters/04-05-time-budget.md)
- [领域知识注入：prompt、工具、代码、数据，各就各位](chapters/04-06-domain-injection.md)

**五 · 数据与真实性**

- [抓取架构：绝不被封，是第一约束](chapters/05-01-scraping.md)
- [真实 vs 编造：数据层的六条铁律](chapters/05-02-real-vs-fake.md)
- [境内外差异：其实是在同时维护两套系统](chapters/05-03-domestic-abroad.md)

**六 · 工程与运维**

- [部署架构：简单，胜过「正确」](chapters/06-01-deploy.md)
- [性能：先量清楚，再动手](chapters/06-02-performance.md)
- [并发能力：先把配置级的榨干](chapters/06-03-scaling.md)
- [调试方法论：一切以可观测的事实为准](chapters/06-04-debugging.md)
- [监控与推送：重要的事，让它来找你](chapters/06-05-monitoring.md)

**七 · 产品化**

- [从工具到产品：每一步都选最轻的方式先跑通](chapters/07-01-tool-to-product.md)
- [平台化：从单机工具到约伴社交](chapters/07-02-platformization.md)
- [冷启动：让广场从第一天起就不空](chapters/07-03-cold-start.md)
- [设计系统：让一个人维护出「一致」](chapters/07-04-design-system.md)

**八 · 方法论沉淀**

- [做专用 Agent 的可复制流程](chapters/08-01-process.md)
- [通用架构 × 专业能力：壁垒在乘号的哪一边](chapters/08-02-general-x-domain.md)
- [踩过的坑：一份专用 Agent 避坑清单](chapters/08-03-lessons.md)
- [这个时代，属于「懂行的人」](chapters/08-04-the-era.md)

---

## 结构

```
building-domain-agents/
  README.md      # 本文件
  chapters/      # 一章一个 .md（YAML frontmatter + markdown）
  assets/        # 图片资源
```

章节是纯 markdown，可在 GitHub 直接读，也由野行 Y 站内 `/methodology` 渲染展示——同一份内容，两处用。

## 关于作者

一个产品经理 + 程序员 + 连续创业者，长期在 AI 领域，同时是个自驾深度爱好者。野行 Y 计划本就是作者发起的真实自驾项目——自己做行程、召集伙伴、开着车出发。这套方法论，是把「结合 AI 把这件事做成一个专用 Agent」的完整实践，写了下来。详见[写在前面的话](chapters/00-00-preface.md)。
