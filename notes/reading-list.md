# Agent 工程实践 10 篇：来源与中文摘要

> 本页提供官方链接与原创摘要，不转载第三方全文。

## 01｜LLM Powered Autonomous Agents

- 作者：Lilian Weng
- 原文：<https://lilianweng.github.io/posts/2023-06-23-agent/>
- 摘要：用规划、记忆和工具建立早期 LLM Agent 的经典结构。今天读它最有价值的方式，是把早期“长期记忆＝向量库”的设想，与后来 Coding Agent 的确定性代码检索做历史对照。

## 02｜Building Effective Agents

- 作者：Anthropic
- 原文：<https://www.anthropic.com/engineering/building-effective-agents>
- 摘要：区分固定代码路径的 Workflow 与模型动态决策的 Agent，建议优先采用简单、可组合的方案，只有任务确实需要时才增加自主性和复杂度。

## 03｜Don’t Build Multi-Agents

- 作者：Cognition
- 原文：<https://cognition.ai/blog/dont-build-multi-agents>
- 摘要：强调共享上下文和“动作携带隐含决策”。连续编码、调试与修改同一组状态时，摘要式交接会损失关键信息，多 Agent 反而可能增加协调错误。

## 04｜How We Built Our Multi-Agent Research System

- 作者：Anthropic
- 原文：<https://www.anthropic.com/engineering/multi-agent-research-system>
- 摘要：说明多 Agent 适合广度优先、相对独立、可压缩汇总的研究任务。并行子 Agent 用各自上下文搜索不同方向，代价是更高 Token、协调和评估成本。

## 05｜Context Engineering for AI Agents: Lessons from Building Manus

- 作者：Manus
- 原文：<https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus>
- 摘要：把上下文当作运行时资源，讨论 KV Cache、文件系统外部记忆、错误保留和复述等实践。重点不是写一次“神奇 Prompt”，而是维护模型每一轮真正需要的信息。

## 06｜Effective Context Engineering for AI Agents

- 作者：Anthropic
- 原文：<https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents>
- 摘要：定义 Context Engineering，并强调上下文并非越长越好。系统需要选择、压缩、即时检索和隔离，减少 context rot 与无关信息对注意力预算的消耗。

## 07｜Writing Effective Tools for AI Agents

- 作者：Anthropic
- 原文：<https://www.anthropic.com/engineering/writing-tools-for-agents>
- 摘要：高质量工具来自清楚的边界、命名、返回内容与评估，而不是工具数量。少量高价值工具通常比把所有 API 都暴露给模型更可靠、更节省上下文。

## 08｜Designing Agentic Loops

- 作者：Simon Willison
- 原文：<https://simonwillison.net/2025/Sep/30/designing-agentic-loops/>
- 摘要：把 Agent 描述为“围绕目标循环调用工具的系统”，强调外层循环、验证器和隔离环境。模型能力越强，循环设计和环境边界越重要。

## 09｜Your AI Product Needs Evals

- 作者：Hamel Husain
- 原文：<https://hamel.dev/blog/posts/evals/>
- 摘要：从单元测试、人工/模型评估、Trace 检查到 A/B 测试，解释为什么没有可重复的 Evals，团队就只能凭感觉调整 Agent。

## 10｜Effective Harnesses for Long-Running Agents

- 作者：Anthropic
- 原文：<https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents>
- 摘要：用 initializer、进度文件、Git、测试与增量交付连接多个上下文窗口。长任务的关键不是无限延长对话，而是给下一次会话留下可验证、可继续的外部状态。

## 对照阅读建议

- **03 + 04**：多 Agent 不是对错问题，而是任务拓扑问题。
- **05 + 06**：把 Manus 的具体实践与 Anthropic 的通用上下文模型对照。
- **07 + 09**：工具契约解决“怎么做”，Evals 解决“怎么知道做对了”。
- **08 + 10**：一个讨论循环，一个讨论跨会话交接，共同构成长任务 Harness。

