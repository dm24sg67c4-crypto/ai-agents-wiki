# AI Agents Wiki（給完全不懂的大學生）

這是一個用「先討論、後生成」方式建立的 LLM Wiki，共 ingest 5 篇來源。所有論述後面的 `[S1.3]` 這類標記，指向 `sources/` 裡對應來源頁的第幾個要點，可以逐句回查。

## 建議閱讀順序

1. [agent](concepts/agent.md)：什麼是 Agent
2. [agent-vs-chatbot](concepts/agent-vs-chatbot.md)：和聊天機器人、Workflow 有何不同
3. [agent-loop](concepts/agent-loop.md)：Agent 怎麼一輪一輪運作
4. [tools](concepts/tools.md)、[memory](concepts/memory.md)、[planning](concepts/planning.md)：三個核心零件
5. [guardrails](concepts/guardrails.md)：怎麼確保它沒走偏
6. [use-cases](applications/use-cases.md)：Agent 能做什麼

## 來源清單

| 編號 | 來源 | 類型 |
|---|---|---|
| S1 | [Anthropic〈Building effective agents〉](sources/S1-anthropic-building-effective-agents.md) | 原廠工程文章 |
| S2 | [OpenAI〈A practical guide to building agents〉](sources/S2-openai-practical-guide-to-building-agents.md) | 原廠實務指南 |
| S3 | [Lilian Weng〈LLM Powered Autonomous Agents〉](sources/S3-weng-llm-powered-autonomous-agents.md) | 技術長文 |
| S4 | [ReAct 論文（Yao 等）](sources/S4-react-paper.md) | 學術論文（僅讀摘要） |
| S5 | [IBM〈AI agent use cases〉](sources/S5-ibm-ai-agent-use-cases.md) | 廠商科普 |

## 已知限制

- S4 只抓到摘要頁，未讀全文。
- S5 為廠商文章，效益數字未經獨立驗證。
- S1、S3 發表於 2024 與 2023 年，工具與模型能力已有變化。
- 未選擇「風險與限制」作為獨立切入角度，相關內容併入 [guardrails](concepts/guardrails.md)。
