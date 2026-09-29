# Gdemoni · 让想法变成可以使用的作品

<p align="center">软件工程专业在读 · 产品架构与 AI 应用实践</p>

<p align="center">
  <a href="https://zshgdemoni.me/">个人网站</a> ·
  <a href="https://github.com/gdemoni">GitHub</a> ·
  <a href="https://x.com/Gdemonizsh">X</a> ·
  <a href="mailto:zhang2718827630@gmail.com">邮箱</a>
</p>

你好，我是 Gdemoni，一名软件工程专业的大三学生。我关注 AI 如何进入真实的产品流程，也喜欢把对工具和交互的好奇心做成可以体验的项目。这个仓库集中介绍我的实习经历与项目实践；更完整的个人记录在 [zshgdemoni.me](https://zshgdemoni.me/)。

## 为什么加入 Pieces Lab

我希望在这里分享自己的个人网站、实习实践与项目经历，结识更多愿意动手创造的人。我的初心是从真实问题出发，把脑海里的想法逐步做出来，并把过程中的尝试、问题与收获记录下来，供彼此交流。

## 实习经历 · Askio 运维排障 AI 助手

**上海七牛信息技术有限公司｜产品架构部 · 产品架构实习生｜2026.05—2026.09**<br>
**五人小组组长，负责整体架构设计、技术选型与 Agent 核心实现。** [查看 Askio 官网 ↗](https://www.askio.site/)

Askio 面向运维排障中“排查方向难追踪、指标与日志证据分散、历史经验难复用”等问题。我们把一次排障组织成可分叉、汇聚和排除方向的调查图，让 Agent 围绕当前证据推进分析，同时保留人工打断与纠偏的入口。

- **调查图与 Agent 工作流：**将排查过程建模为“根节点 → 排查节点 → 故障域”，由 Agent 拆解问题、调用指标、日志和 Trace 工具，并在信息不足时继续追问。
- **经验沉淀与复用：**把已完成的调查压缩为“故障现象 → 故障域 → 排障思路”的结构，通过 RAG 召回相似经验，再用当前数据重新验证。
- **系统架构：**以调查图变更、消息增量、工具调用等事件协调前后端，并通过 SSE 推送进展；基于 NestJS、Fastify、ts-rest 与 Zod 组织 HTTP / SSE 接口合同，使用 PostgreSQL / pgvector、BullMQ / Redis 支撑存储与异步任务。

这段实习让我从单个功能的实现走向系统层面的设计：既要让 Agent 有清晰的决策与取证路径，也要让用户看得懂、能介入整个排障过程。

## 项目经历

### [EduAvatar · 课程教学数字人](https://github.com/gdemoni/EduAvatar)

面向课程辅导的多模态 AI 数字人。学生提出语音问题后，系统完成语音识别，使用 LangGraph 区分知识讲解、题目求解等场景，结合课程资料检索生成回答，再通过语音合成、唇形同步与 WebRTC 在浏览器中呈现讲解。

我重点实践了 **Agent 分场景编排、课程 RAG 和多模态交互链路**：使用 BGE + FAISS 检索本地课程资料，未命中时补充网络搜索；把生成答案改写为适合朗读的内容，再串联 EdgeTTS、Wav2Lip 与浏览器音视频传输。[项目 Wiki](https://github.com/gdemoni/EduAvatar/wiki)记录了搭建过程。

### [Travel Agent · 多 Agent 旅行助手](https://github.com/gdemoni/agent_ctrip_assistant)

围绕航班、酒店、租车和旅行推荐，使用 LangGraph / LangChain 组织 **1 个主助理与 4 个领域助理**。主助理理解需求并委派任务；查询工具可以直接执行，预订、改签、取消等修改类操作在执行前暂停，等待用户确认。

后端还实现了政策 FAQ 的 BM25 + BGE 混合检索与重排，并使用 FastAPI 提供工作流接口。项目目前主要展示后端编排、检索与服务设计，前端仍在开发中；仓库中的业务数据为示例数据，不提供真实订票服务。

### [Gdemoni Mail · 自建域名邮箱](https://github.com/gdemoni/cloud-mail)

基于开源项目 Cloud Mail，在自己的域名上部署和维护 [@zshgdemoni.me 邮箱服务](https://mail.zshgdemoni.me/)。这是一项**开源项目部署与运维实践**：我负责自有域名接入、部署与日常维护；邮件收发等基础能力来自原项目。通过它，我进一步熟悉了 Cloudflare Workers、D1 / KV / R2 等服务的组合与实际运行。

## 持续学习

我正在继续学习 TypeScript、Java 和 Go，也持续体验 AI 开发工具。比起罗列技术名词，我更希望通过项目说明自己如何理解问题、做出选择，并把一个想法逐步推进为可以使用的东西。

欢迎访问我的[个人网站](https://zshgdemoni.me/)了解更多，也可以通过 [GitHub](https://github.com/gdemoni)、[X](https://x.com/Gdemonizsh) 或[邮件](mailto:zhang2718827630@gmail.com)与我交流。
