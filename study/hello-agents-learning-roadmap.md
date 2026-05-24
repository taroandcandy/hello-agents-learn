# Hello-Agents 项目学习路线

生成日期：2026-05-24

本文基于 Datawhale Hello-Agents 在线教程和当前本地仓库结构整理，目标是把 `hello-agents-learn` 项目从“章节目录”变成一条可以按周推进、能产出代码和笔记的学习路线。

参考来源：

- Datawhale Hello-Agents 在线教程：https://hello-agents.datawhale.cc/#/
- Hello-Agents GitHub 仓库：https://github.com/datawhalechina/Hello-Agents
- 当前本地项目：`D:\front\agent\hello-agents-learn`

## 1. 项目定位

Hello-Agents 是一本“从零开始构建智能体”的系统教程。它不是只讲怎么调用某个 Agent 框架，而是按下面这条主线展开：

```text
Agent 概念与 LLM 基础
-> 经典 Agent 范式
-> 低代码平台与主流框架
-> 自研 Agent 框架
-> 记忆、RAG、上下文工程、协议、训练、评估
-> 旅行助手、DeepResearch、赛博小镇
-> 落地 Agent 项目
```

当前仓库的学习资源主要分布在：

```text
docs/                  正文教程，按 16 章组织
code/                  每章配套代码
Extra-Chapter/         扩展材料、FAQ、面试、环境配置、踩坑总结
Co-creation-projects/  社区共创落地项目参考
Additional-Chapter/    n8n、Node.js 等补充安装文档
study/                 你自己的学习笔记与配置记录
```

## 2. 推荐学习节奏

如果你只是想快速建立 Agent 应用能力，建议按 6 周走完主线；如果你想扎实掌握并做出一个可落地的 Agent 项目，建议按 8 到 10 周推进。

```text
第 0 阶段：环境与项目熟悉，0.5 天
第 1 阶段：智能体与 LLM 基础，2 到 3 天
第 2 阶段：经典范式与低代码平台，4 到 6 天
第 3 阶段：框架实践与自研 Agent 框架，1 到 2 周
第 4 阶段：记忆、RAG、上下文工程，1 到 2 周
第 5 阶段：协议、训练、评估，1 到 2 周
第 6 阶段：综合案例，1 到 2 周
第 7 阶段：落地 Agent 项目，长期迭代
```

## 3. 第 0 阶段：环境与项目地图

目标：先知道项目里有什么、代码怎么跑、笔记放哪里。

建议阅读：

```text
README.md
docs/README.md
docs/前言.md
Extra-Chapter/Extra07-环境配置.md
Additional-Chapter/NODEJS_INSTALL_GUIDE.md
Additional-Chapter/N8N_INSTALL_GUIDE.md
```

本地重点路径：

```text
docs/_sidebar.md
code/
study/
```

建议产出：

```text
study/00-project-map.md
```

里面记录三件事：

```text
1. 16 章分别解决什么问题
2. 哪些章节有配套代码
3. 自己最想做的落地 Agent 项目方向
```

验收标准：

```text
可以用自己的话讲清楚 docs、code、Extra-Chapter、Co-creation-projects 的作用。
```

## 4. 第 1 阶段：智能体与语言模型基础

对应章节：

```text
docs/chapter1/第一章 初识智能体.md
docs/chapter2/第二章 智能体发展史.md
docs/chapter3/第三章 大语言模型基础.md
```

配套代码：

```text
code/chapter1/
code/chapter2/
code/chapter3/
```

学习重点：

```text
Agent 的定义、环境、感知、行动
Workflow 和 Agent 的差异
符号主义到 LLM Agent 的演进
Transformer、Embedding、Tokenization、提示词与主流 LLM
```

动手任务：

```text
1. 跑通 code/chapter1/FirstAgentTest.py 或对应 notebook。
2. 阅读 code/chapter2/ELIZA.py，理解早期对话系统和现代 LLM Agent 的差异。
3. 跑通 chapter3 中 BPE、N-gram、Embedding、Transformer 的示例。
```

建议产出：

```text
study/01-agent-and-llm-basics.md
```

验收标准：

```text
能解释“Agent 不只是一次 LLM 调用”，而是由目标、状态、工具、行动循环共同构成的系统。
```

## 5. 第 2 阶段：经典范式与低代码 Agent

对应章节：

```text
docs/chapter4/第四章 智能体经典范式构建.md
docs/chapter5/第五章 基于低代码平台的智能体搭建.md
```

配套代码：

```text
code/chapter4/ReAct.py
code/chapter4/Plan_and_solve.py
code/chapter4/Reflection.py
code/chapter4/tools.py
code/chapter5/
```

学习重点：

```text
ReAct：思考、行动、观察的循环
Plan-and-Solve：先规划再执行
Reflection：执行后自我反思和修正
Coze、Dify、n8n 这类低代码平台的适用边界
```

动手任务：

```text
1. 分别运行 ReAct、Plan-and-Solve、Reflection 示例。
2. 给 tools.py 增加一个自己的工具，例如文件搜索、计算器或网页摘要。
3. 用 n8n 或 Dify 复现一个简单流程型 Agent。
```

建议产出：

```text
study/02-agent-patterns.md
```

验收标准：

```text
能判断一个任务更适合 Workflow、ReAct、Plan-and-Solve 还是 Reflection。
```

## 6. 第 3 阶段：主流框架与自研 Agent 框架

对应章节：

```text
docs/chapter6/第六章 框架开发实践.md
docs/chapter7/第七章 构建你的Agent框架.md
```

配套代码：

```text
code/chapter6/
code/chapter7/
```

学习重点：

```text
AutoGen、AgentScope、LangGraph 的基本使用
LLM 封装、Agent 抽象、工具注册、执行循环
SimpleAgent、ReActAgent、ReflectionAgent、PlanAndSolveAgent
自研框架和第三方框架的取舍
```

动手任务：

```text
1. 跑通 code/chapter6 里的至少一个框架案例。
2. 跑通 code/chapter7/my_main.py。
3. 给自研框架新增一个工具，并让 Agent 自动调用。
4. 写一个最小版“资料查询助手”或“代码解释助手”。
```

建议产出：

```text
study/03-agent-framework-notes.md
```

验收标准：

```text
能画出一个 Agent 框架的核心模块：LLM、Prompt、Tool、Memory、Planner、Executor。
```

## 7. 第 4 阶段：记忆、RAG 与上下文工程

对应章节：

```text
docs/chapter8/第八章 记忆与检索.md
docs/chapter9/第九章 上下文工程.md
```

配套代码：

```text
code/chapter8/
code/chapter9/
```

学习重点：

```text
短期记忆、长期记忆、工作记忆
RAG pipeline：切分、向量化、检索、重排、生成
上下文压缩、上下文构建、任务状态维护
持续交互中如何避免上下文失控
```

动手任务：

```text
1. 跑通 code/chapter8/10_RAG_Pipeline_Complete.py。
2. 跑通 code/chapter8/11_Q&A_Assistant.py。
3. 阅读 code/chapter9 的 context builder 示例。
4. 用本项目 docs 做一个最小 RAG 问答助手。
```

建议产出：

```text
study/04-memory-rag-context.md
```

验收标准：

```text
能说明“把全部历史塞进 prompt”为什么不是好的上下文工程。
```

## 8. 第 5 阶段：协议、训练与评估

对应章节：

```text
docs/chapter10/第十章 智能体通信协议.md
docs/chapter11/第十一章 Agentic-RL.md
docs/chapter12/第十二章 智能体性能评估.md
```

配套代码：

```text
code/chapter10/
code/chapter11/
code/chapter12/
```

学习重点：

```text
MCP：工具和外部能力接入协议
A2A、ANP：智能体间通信与协作
SFT、LoRA、GRPO、奖励函数
Agent 评估指标、基准测试、错误分析
```

动手任务：

```text
1. 跑通 code/chapter10 的 MCP 或 A2A 示例。
2. 阅读 code/chapter10/weather-mcp-server，理解一个 MCP Server 的结构。
3. 在 chapter11 中先跑 quick test，不急着做大规模训练。
4. 用 chapter12 的评估思路给自己前面做的小 Agent 设计 3 个测试用例。
```

建议产出：

```text
study/05-protocol-training-evaluation.md
```

验收标准：

```text
能区分“功能可用”和“系统可评估”，并能给 Agent 设计基本评测集。
```

## 9. 第 6 阶段：综合案例进阶

对应章节：

```text
docs/chapter13/第十三章 智能旅行助手.md
docs/chapter14/第十四章 自动化深度研究智能体.md
docs/chapter15/第十五章 构建赛博小镇.md
```

配套代码：

```text
code/chapter13/
code/chapter14/helloagents-deepresearch/
code/chapter15/Helloagents-AI-Town/
```

学习重点：

```text
多智能体分工
工具调度和任务规划
前后端结合的 Agent 应用
长期状态和模拟社会行为
```

动手任务：

```text
1. 优先跑 chapter14 的 DeepResearch 项目，因为它最接近真实 Agent 应用。
2. 拆解它的后端服务、工具系统、任务规划、总结和报告生成链路。
3. 再选择 chapter13 或 chapter15 做一个方向拓展。
```

建议产出：

```text
study/06-case-study-deepresearch.md
```

验收标准：

```text
能从需求出发，拆出 Agent 角色、工具、状态、任务流和评估方式。
```

## 10. 第 7 阶段：落地 Agent 项目设计

对应章节：

```text
docs/chapter16/第十六章 毕业设计.md
code/chapter16/共创路径.md
Co-creation-projects/
```

这里把教程中的毕业设计章节当作项目设计参考，真正目标是做一个可运行、可评估、能逐步迭代的落地 Agent 项目。项目建议从小而完整开始，不要一上来做“大而全平台”。

推荐方向：

```text
1. 个人学习助手：读取仓库文档，生成学习计划、测验和复习卡片。
2. 代码评审助手：读取变更 diff，输出风险、建议和测试点。
3. 数据分析助手：读取 CSV，自动做探索分析和报告。
4. 旅行规划助手：结合搜索、约束、偏好，输出可执行行程。
5. 知识库问答助手：把 docs 做成 RAG，并支持来源引用。
```

项目最小闭环：

```text
输入：用户问题或任务
规划：拆解步骤
工具：至少 2 个外部工具或本地工具
记忆：保存任务状态或用户偏好
输出：结构化结果
评估：至少 5 条固定测试用例
```

建议产出：

```text
study/07-agent-project-plan.md
```

验收标准：

```text
有一个可以从命令行或 Web 页面运行的 Agent Demo，并有 README、示例输入输出和测试记录。
```

## 11. 扩展学习顺序

主线学完后，再看 `Extra-Chapter` 更合适。推荐顺序：

```text
Extra07-环境配置.md
Extra04-DatawhaleFAQ.md
Extra02-上下文工程补充知识.md
Extra05-AgentSkills解读.md
Extra08-如何写出好的Skill.md
Extra09-Agent应用开发实践踩坑与经验分享.md
Extra10-Agent自进化.md
Extra11-WebAgent科普与实战.md
Extra12-旅行助手后训练实战.md
Extra01-面试问题总结.md
Extra01-参考答案.md
```

`Co-creation-projects` 不建议一开始就逐个精读。更好的方式是：先确定自己的落地 Agent 项目方向，再找 2 到 3 个类似项目拆解目录结构、依赖、Agent 设计和 README 写法。

## 12. 推荐笔记体系

建议把自己的笔记都放在 `study/` 下，按阶段命名：

```text
study/00-project-map.md
study/01-agent-and-llm-basics.md
study/02-agent-patterns.md
study/03-agent-framework-notes.md
study/04-memory-rag-context.md
study/05-protocol-training-evaluation.md
study/06-case-study-deepresearch.md
study/07-agent-project-plan.md
```

每篇笔记固定写四块：

```text
1. 本章解决什么问题
2. 我跑通了哪些代码
3. 我改了什么
4. 还能继续做什么
```

## 13. 当前优先级建议

结合你现在已经在整理 `study/`、配置 Git 和终端环境，最自然的下一步是：

```text
1. 先写 study/00-project-map.md，建立项目地图。
2. 跑 code/chapter1/FirstAgentTest.py。
3. 读 chapter4，并跑 ReAct、Plan-and-Solve、Reflection。
4. 读 chapter7，开始理解自研 Agent 框架。
5. 直接进入 chapter8/chapter9，用 docs 做一个小型 RAG 问答助手。
```

这个顺序会比从第 1 章一直读到第 16 章更有手感。Hello-Agents 的价值在于边读边改代码；每完成一个阶段，都应该留下一个能运行的小东西。

## 14. 每周执行版路线

如果每周能投入 8 到 12 小时，可以按下面的节奏推进。每周不要只读文档，至少要有一次代码运行、一次代码修改和一次笔记整理。

```text
第 1 周：项目地图 + Agent/LLM 基础 + 第一个 Agent 示例
第 2 周：ReAct、Plan-and-Solve、Reflection 三种范式
第 3 周：主流框架初体验 + 自研 Agent 框架跑通
第 4 周：RAG pipeline + 基于 docs 的知识库问答
第 5 周：上下文工程 + MCP/A2A 协议入门
第 6 周：评估体系 + 给自己的 Agent 做测试集
第 7 周：DeepResearch 案例拆解
第 8 周：落地 Agent 项目第一版
第 9-10 周：补齐记忆、工具、评估、README 和演示记录
```

每周固定交付物：

```text
1. 一篇学习笔记
2. 一个可运行脚本或 Demo
3. 一次小改动，例如新增工具、改 prompt、替换模型或增加测试用例
4. 一个复盘结论：本周最重要的概念、最容易踩坑的地方、下周继续做什么
```

## 15. 每天学习动作模板

每天学习时建议按 60 到 120 分钟切块，不要一上来连续啃很长文档。

```text
10 分钟：回顾上次笔记，确认今天目标
30 分钟：阅读对应章节，标记关键概念
30 分钟：运行配套代码，记录运行命令和报错
20 分钟：做一个小修改，观察输出变化
10 分钟：写当天笔记和下一步问题
```

当天笔记可以直接使用这个模板：

```markdown
# 日期

## 今天目标

## 阅读内容

## 运行命令

## 运行结果

## 我改了什么

## 遇到的问题

## 明天继续
```

## 16. 代码运行记录规范

学习 Agent 项目很容易出现“当时跑通了，过两天忘了怎么跑”的问题。建议每次跑代码都留下最小记录。

```text
章节：
文件：
运行目录：
运行命令：
依赖安装：
环境变量：
输入样例：
输出摘要：
是否成功：
问题记录：
```

如果涉及 API Key，不要把真实 Key 写进笔记。只记录变量名，例如：

```text
OPENAI_API_KEY
DASHSCOPE_API_KEY
DEEPSEEK_API_KEY
```

## 17. 阶段复盘问题

每完成一个阶段，用下面这些问题做一次小复盘。能答清楚，才进入下一阶段；答不清楚，就回到代码再跑一次。

```text
1. 这个阶段解决的核心问题是什么？
2. 这一阶段的 Agent 能力边界在哪里？
3. 我跑通了哪些代码？运行入口在哪里？
4. 我做过哪些修改？修改后行为有什么变化？
5. 这个阶段最常见的失败模式是什么？
6. 如果把它放进落地 Agent 项目，能承担什么模块？
```

各阶段重点追问：

```text
第 1 阶段：我能不能讲清楚 Agent、Workflow、LLM 调用三者的区别？
第 2 阶段：我能不能为一个任务选择合适的 Agent 范式？
第 3 阶段：我能不能解释 Agent 框架里 LLM、Tool、Memory、Executor 的关系？
第 4 阶段：我能不能从零搭出一个最小 RAG pipeline？
第 5 阶段：我能不能给 Agent 设计测试用例，而不是只看一次输出好不好？
第 6 阶段：我能不能拆解一个真实案例的任务流、工具流和状态流？
第 7 阶段：我能不能把落地 Agent 项目压缩成一个两周内可用的第一版？
```

## 18. 落地 Agent 项目推进表

这个项目不是为了交作业，而是作为学习 Agent 的入口：边学教程，边把概念沉淀到一个真实可用的小系统里。建议从第 4 阶段结束后就建立 `study/07-agent-project-plan.md`，先做一个很小但闭环的版本。

```text
第 0 版：明确真实使用场景、目标用户和输入输出
第 1 版：只支持命令行输入输出，先跑通一次完整任务
第 2 版：接入 1 到 2 个工具，例如本地文件读取、搜索、计算或代码分析
第 3 版：增加 RAG 或上下文构建，让 Agent 能用自己的资料回答问题
第 4 版：增加简单记忆或任务状态，让连续任务不丢上下文
第 5 版：增加固定测试集和评估记录，避免只凭感觉判断效果
第 6 版：整理 README、示例输入输出、运行脚本和演示截图
```

推荐的第一版规格：

```text
功能：只解决一个高频、真实、可重复的问题
入口：命令行或一个简单 Web 页面
工具：本地文件读取 + 一个外部能力
记忆：先用 JSON 或 SQLite 保存，不急着上复杂数据库
评估：先写 5 条固定问题，记录预期输出和实际输出
文档：README 里写清安装、运行、示例和已知限制
```

适合作为学习入口的落地方向：

```text
1. Hello-Agents 学习助手：读取 docs 和 study，回答章节问题，生成学习任务和复习卡片。
2. 本地代码理解助手：读取指定文件或 diff，解释代码、指出风险、给出测试建议。
3. 个人知识库问答助手：读取自己的 Markdown 笔记，支持来源引用和追问。
4. 任务拆解助手：输入一个目标，输出执行步骤、依赖、检查清单和复盘问题。
```

最推荐从“Hello-Agents 学习助手”开始，因为它正好复用当前仓库资料，能同时练到 RAG、工具调用、上下文工程、评估和 README 写法。

## 19. 常见卡点与处理方式

```text
API 调不通：
先确认环境变量、模型名、base_url，再用最小请求测试，不要直接在复杂 Agent 里排查。

依赖装不上：
记录 Python/Node 版本、安装命令和完整报错，优先看项目 README 和 Extra07 环境配置。

代码能跑但看不懂：
先找入口文件，再按输入、状态、工具调用、模型调用、输出五条线拆。

输出不稳定：
固定 temperature、固定输入样例，保存一次成功输出和一次失败输出做对比。

RAG 效果差：
先检查切分、召回结果和引用来源，不要只改 prompt。

落地项目变大：
把功能砍回一个输入、一个任务流、一个结构化输出，先保证闭环。
```

## 20. 下一步最小行动清单

从现在开始，建议先做这 5 件事：

```text
1. 新建 study/00-project-map.md，按章节列出 docs 和 code 的对应关系。
2. 维护 study/07-agent-project-plan.md，把落地项目先定为 Hello-Agents 学习助手。
3. 跑通 code/chapter1/FirstAgentTest.py，并记录运行命令。
4. 阅读 chapter4，分别运行 ReAct、Plan-and-Solve、Reflection。
5. 修改 code/chapter4/tools.py，增加一个最简单的本地文档读取或搜索工具。
```

完成这 5 件事后，再进入 chapter7 的自研 Agent 框架，并把里面的 LLM、Tool、Memory、Executor 设计迁移到自己的学习助手里，会比直接看框架源码顺很多。
