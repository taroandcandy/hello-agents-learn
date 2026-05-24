# 落地 Agent 项目计划

本文用于记录从 Hello-Agents 学习路线中孵化出来的真实 Agent 项目。目标不是做课程作业，而是做一个能持续迭代、能解决实际问题的小型 Agent 系统。

## 1. 项目方向

推荐第一版项目：

```text
Hello-Agents 学习助手
```

它的目标是读取当前仓库中的 `docs/`、`code/` 和 `study/`，帮助学习者完成三件事：

```text
1. 回答 Hello-Agents 章节相关问题，并给出来源路径。
2. 根据当前学习阶段生成下一步学习任务。
3. 把学习内容整理成复习卡片、检查清单或阶段复盘问题。
```

选择这个方向的原因：

```text
1. 数据就在当前仓库里，不需要一开始接复杂外部系统。
2. 能练到 RAG、工具调用、上下文工程、评估和 README 写法。
3. 学习过程本身会不断产生新笔记，项目可以自然迭代。
4. 做出来以后自己真的能用，而不是只跑一次示例。
```

## 2. 第一版目标

第一版只做命令行版本，先保证闭环。

```text
输入：一个学习问题或任务
检索：从 docs/ 和 study/ 中找到相关内容
推理：结合问题生成回答、学习建议或复习清单
输出：结构化 Markdown
引用：列出使用到的本地文件路径
评估：准备 5 条固定问题，记录回答质量
```

第一版暂时不做：

```text
1. 不做复杂 Web 页面。
2. 不做多用户系统。
3. 不做长期聊天记录。
4. 不做复杂权限和账号体系。
5. 不追求一次性支持所有章节。
```

## 3. 功能拆分

```text
P0 项目骨架：
建立项目目录、README、运行命令和配置说明。

P1 文档读取工具：
读取 docs/、study/ 下的 Markdown 文件，返回文件路径、标题和正文片段。

P2 简单检索：
先用关键词检索或朴素文本匹配，确认输入到输出的链路跑通。

P3 RAG 检索：
加入切分、Embedding、向量检索和来源引用。

P4 Agent 编排：
让 Agent 根据用户问题选择工具，例如查章节、总结笔记、生成任务。

P5 评估集：
固定 5 到 10 条问题，记录预期点、实际输出和改进记录。

P6 可用性整理：
补 README、示例输入输出、常见问题和演示截图。
```

## 4. 推荐目录

可以先放在仓库根目录下的 `agent_project/`，避免和教程原始代码混在一起。

```text
agent_project/
  README.md
  pyproject.toml 或 requirements.txt
  .env.example
  src/
    main.py
    config.py
    loaders.py
    retrieval.py
    tools.py
    agent.py
    prompts.py
  data/
    index/
  evals/
    questions.md
    results.md
```

## 5. 最小运行命令

第一版期望最终能这样运行：

```powershell
python -m src.main "我应该如何学习 Hello-Agents 的 ReAct 部分？"
```

输出示例结构：

```markdown
## 回答

## 推荐下一步

## 复习问题

## 来源
```

## 6. 固定评估问题

先用这 5 条问题作为第一批评估集：

```text
1. Agent 和普通 LLM 调用有什么区别？
2. ReAct、Plan-and-Solve、Reflection 分别适合什么任务？
3. 为什么 RAG 不能只靠把全部文档塞进 prompt？
4. 如果我要做一个学习助手，至少需要哪些工具？
5. 学完 chapter7 后，应该怎样理解自研 Agent 框架？
```

每次迭代后记录：

```text
问题：
预期回答要点：
实际输出摘要：
来源是否正确：
是否有幻觉：
下一步修改：
```

## 7. 近期行动清单

```text
1. 跑通 chapter1 的第一个 Agent 示例。
2. 跑通 chapter4 的 ReAct 示例。
3. 新建 agent_project/README.md，写清项目目标和第一版范围。
4. 写一个 Markdown 文件读取工具，能列出 docs/ 下的章节标题。
5. 用关键词检索先做出第一个可回答问题的命令行版本。
```
