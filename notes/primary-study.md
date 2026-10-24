# 主要研究摘要：11 套 Coding Agent Harness 的源码解剖

## 研究

Paul Barbaste、Tristan Darrigol、Germain Vu、Tom Wiltberger：

**Harness Engineering: Anatomy, Architecture, and Evolution of Coding Agents — A Source-Code Study of Eleven Systems**

- arXiv：<https://arxiv.org/abs/2609.00006>
- 时间：2026 年 7 月
- 类型：源码研究 / 预印本
- 范围：约 400 万行 Python、TypeScript 与 Rust

## Harness 的定义

论文把 Harness 定义为“模型之外的一切”：把 LLM 连接到真实世界的运行时，包括循环、工具、上下文、安全控制、编排与扩展面。

## 七个子系统

1. Agent Loop
2. LLM 集成
3. 工具与动作
4. 记忆与上下文
5. 安全与权限
6. 编排
7. 扩展机制

## 研究对象

Claude Code、Codex CLI、Gemini CLI、Mistral Vibe、OpenHands、Aider、Mini-SWE-Agent、Hermes、Pi、OpenCode、OpenClaw；Omnigent 作为 Meta-Harness 对照。

## 九个值得记住的发现

1. Loop 复杂度不直接预测任务表现。百行级 Harness 可以完成基本任务；生产系统的大量代码服务于异常路径、安全、恢复、上下文、扩展和客户端。
2. 在这 11 套系统及固定版本中，核心运行时没有使用 LangChain、LangGraph、AutoGen、CrewAI 等通用 Agent 框架。
3. 同一固定样本中，没有系统用向量嵌入检索代码；常见方案是 ripgrep、glob、tree-sitter、LSP、路径与 Markdown 上下文。
4. 生产系统围绕事件日志、策略即代码、子 Agent、延迟加载、即时上下文、压缩、检查点和外层验证等模式收敛。
5. 安全不是代码量增加后的自然副产品，而是必须单独设计的工程层。
6. 多 Agent 多采用 coordinator-worker；开放协议更多出现在 IDE、宿主或 Meta-Harness 边界。
7. Skills 的采用达到 9/11，MCP 为 8/11。二者分别偏向流程知识与外部系统连接。
8. Harness 正从命令行工具变成平台：SDK、市场、状态迁移、企业治理与跨 Harness 编排陆续出现。
9. 论文给出 18 条建议和一个约 90 行的最小 Harness，强调先从简单循环、少量工具和确定性检索开始。

## 研究边界

- 这是架构研究，不是同一模型、同一任务下的性能排名。
- “0/11”只适用于论文选择的系统与版本。
- Claude Code 部分基于 2026 年 3 月流传的源码快照，可复现强度低于公开仓库。
- 论文自己注明，部分市场事件没有做源码级核验；引用时应回到官方来源。

