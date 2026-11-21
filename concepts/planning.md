# 規劃（Planning）

## 任務分解

- 把大任務拆成小步驟，常見做法有 Chain of Thought（要求模型逐步思考）、Tree of Thoughts（每步探索多種想法）、以及 LLM+P（把長期規劃外包給傳統規劃器）[S3.2]。
- Anthropic 描述 agent 在任務明確之後會自行規劃並獨立執行，必要時回頭向人類要資訊或請求判斷 [S1.6]。

## 自我反思

- 自我反思讓 agent 回顧過去行動、修正錯誤，在必然會試誤的真實任務中很重要 [S3.3]。
- Reflexion 會偵測軌跡是否低效或出現幻覺，其中幻覺指連續出現相同動作卻得到相同觀察 [S3.4]。

## 讓規劃看得見

Anthropic 的三原則之一是透明：明確呈現 agent 的規劃步驟 [S1.9]。

## 多個 agent 分工

- 複雜任務可由中央 LLM 動態拆解、分派給工作者再彙整（orchestrator-workers）[S1.4]。
- OpenAI 的 Manager 模式是由一個中央 agent 把其他 agent 當工具呼叫；Decentralized 模式則讓 agent 之間用 handoff 交棒 [S2.8]。

## 目前的限制

在冗長歷史上做長期規劃、有效探索解法空間仍然困難；LLM 遇到意外錯誤時，不易調整計畫 [S3.10]。

相關：[agent-loop](agent-loop.md)、[guardrails](guardrails.md)。
