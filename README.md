# Agent Harness Engineering Reading Kit

一套面向 Agent 工程实践者的开源阅读与复现资料，围绕一个核心问题：

> 模型给出能力上限，什么把能力变成稳定、可验证、可恢复的交付？

本项目整理了：

- 一份针对 11 套生产级 Coding Agent Harness 的源码研究；
- 10 篇来自 Lilian Weng、Anthropic、Cognition、Manus、Simon Willison 与 Hamel Husain 的工程文章；
- 两组资料的中文摘要、对照矩阵与建设清单；
- 一篇中文深度文章及 6 个原创视觉节点。

## 核心结论

固定样本中的生产 Harness 没有把主要复杂度放在“更复杂的 Agent 框架”上，而是放在五个闭环：

1. **上下文闭环**：选择、压缩、检索与跨会话交接；
2. **工具闭环**：少量高价值工具、清晰契约与结果回传；
3. **验证闭环**：测试、Lint、截图、哈希、外部回读和停止条件；
4. **权限闭环**：策略、审批、沙盒、审计和默认拒绝；
5. **持久状态闭环**：Git、进度文件、事件日志、检查点与恢复。

源码研究中的两个醒目发现是：在所选 11 套系统及固定版本中，核心运行时 **0/11** 使用通用 Agent 框架，**0/11** 使用向量嵌入检索代码。这是样本结论，不代表所有 Agent 产品，也不意味着框架或向量检索没有适用场景。

## 仓库结构

```text
.
├── article/
│   ├── article.md              # 中文深度文章
│   └── assets/                 # 原创图表与架构示意
├── notes/
│   ├── primary-study.md        # 83 页源码研究摘要
│   ├── reading-list.md         # 10 篇工程文章索引与中文摘要
│   ├── comparison-matrix.md    # 两组资料的交叉对照
│   └── build-checklist.md      # 从原型到生产的检查清单
├── SOURCES.md                  # 完整来源与引用用途
└── LICENSE                     # 本仓库原创内容许可
```

## 推荐阅读顺序

1. 先读 [`notes/primary-study.md`](notes/primary-study.md)，建立 Harness 的七子系统地图；
2. 再读 [`notes/reading-list.md`](notes/reading-list.md) 中的 02、06、07、09、10；
3. 对照阅读 03 与 04，理解单 Agent / 多 Agent 的任务边界；
4. 用 [`notes/build-checklist.md`](notes/build-checklist.md) 检查自己的系统；
5. 最后读 [`article/article.md`](article/article.md)，查看完整论证与建设建议。

## 版权与再分发

本仓库**不重新分发**无明确许可的第三方论文或网页全文，只提供：

- 官方来源链接；
- 我们原创的中文摘要、评论和对照矩阵；
- 脱敏实验记录；
- 原创文章与图表。

第三方作品版权归各自作者或机构所有。请通过 [`SOURCES.md`](SOURCES.md) 中的官方链接阅读原文。

## 适合谁

- 正在搭建 Coding Agent 或业务 Agent 的工程师；
- 需要评估 Agent 平台、权限和治理的技术负责人；
- 想理解 Skills、MCP、多 Agent、上下文与 Evals 如何组合的产品经理；
- 希望从 Demo 走向生产闭环的独立开发者。

## 贡献

欢迎提交 Issue 或 PR：

- 补充新的生产 Harness 证据；
- 修正来源、数字或版本边界；
- 分享可公开复现的 Harness 审计案例；
- 提供不同任务拓扑下的单 Agent / 多 Agent 对照结果。

请不要提交未经授权转载的第三方全文、私有 Prompt、客户数据或凭证。

## 作者

整理与评论：[Jason Kou](https://github.com/Jason-Kou)
