# 什麼是 AI Agent

**一句話**：Agent 是一個以 LLM 為核心、能自己決定下一步、使用工具，並把多步驟任務做完的系統。

> 〔比喻，非來源內容〕可以把它想成一位會自己查資料、跑腿、做完再回報的實習生，而不只是回答問題的百科全書。

## 各家怎麼定義

- OpenAI 把 agent 定義為獨立代替使用者完成任務的系統 [S2.1]。
- Anthropic 的重點在控制權：agent 是 LLM 動態決定自己的流程與工具使用，並自己掌控如何完成任務 [S1.1]。
- IBM 強調能力組合：能規劃、做決策、使用工具、保留上下文並完成多步驟任務 [S5.1]。

## 兩個判斷特徵

1. 用 LLM 管理工作流程並做決策，能辨識任務何時完成、主動修正，失敗時可中止並把控制權交還使用者 [S2.3]。
2. 能存取工具，依當前狀態動態選擇，且在清楚定義的護欄內運作 [S2.3]。

## 由哪些零件組成

- OpenAI 的三件式：Model（推理的 LLM）、Tools（外部函式或 API）、Instructions（行為與護欄的明確指示）[S2.5]。
- Weng 的三件式：LLM 當大腦，搭配規劃、記憶、工具使用 [S3.1]。
- Anthropic 的最小單元是 augmented LLM：LLM 加上檢索、工具、記憶 [S1.2]。

詳見：[agent-loop](agent-loop.md)、[tools](tools.md)、[memory](memory.md)、[planning](planning.md)。

## 名詞邊界各家不同（需注意）

- OpenAI 明說簡單聊天機器人、單輪 LLM 不算 agent [S2.2]，但 IBM 的分類裡連 simple reflex（只依單一規則行動、沒有記憶）也算 agent 類型之一 [S5.4]。
- Anthropic 刻意用「agentic systems」涵蓋所有變體，再區分 workflows 與 agents [S1.1]。

所以讀到「agent」一詞時，要先確認作者指的是哪一種範圍。
