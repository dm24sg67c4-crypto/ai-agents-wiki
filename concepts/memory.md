# 記憶（Memory）

## 兩種記憶

- **短期記憶**：對應 in-context learning，受限於 Transformer 有限的 context window [S3.5]。
- **長期記憶**：對應外部向量資料庫，透過快速檢索（近似最近鄰搜尋）取用 [S3.5]。

## 為什麼重要

- Anthropic 把記憶列為 augmented LLM 的三種增強之一，模型能自己決定要保留哪些資訊 [S1.2]。
- IBM 指出 agent 會跨互動儲存記憶，因此能隨時間改善推理與準確度 [S5.3]。
- Reflexion 把自我反思放進 agent 的動態記憶，用來影響後續決策 [S3.3]。

## 限制

context 長度有限，會限制能放進去的歷史資訊、詳細指令與 API 回應；向量檢索雖能存取更大的知識池，但表達能力不如完整的注意力機制 [S3.10]。

> 〔連結本作業〕LLM Wiki 本身就是一種「長期記憶」：把整理好的知識放在 context 之外，需要時再查詢。這是本專案的類比，不是來源的說法。

相關：[planning](planning.md)、[agent-loop](agent-loop.md)。
