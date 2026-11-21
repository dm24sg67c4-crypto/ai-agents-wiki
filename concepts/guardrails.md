# 護欄與檢查（Guardrails & Checks）

Agent 會自己行動，所以必須有機制確保它「沒走偏」。來源提出了幾層做法：

## 1. 流程中的檢查點

- prompt chaining 可在中間步驟加上程式檢查（gate），確保流程仍在軌道上 [S1.4]。
- 每一步都從環境取得 ground truth 來評估進度 [S1.6]。

## 2. 分層護欄

OpenAI 主張護欄要分層：單一護欄通常不夠，混合多種才更穩 [S2.9]。類型包括 relevance classifier、safety classifier、PII filter、moderation、tool safeguards、rules-based protections、output validation [S2.9]。其中 tool safeguards 依工具風險（讀寫、可否還原、金額影響等）給低／中／高評級，再決定是否暫停檢查或升級給人 [S2.9]。

## 3. 人類介入

兩個主要觸發條件：失敗次數超過門檻，以及高風險動作 [S2.10]。

## 4. 沙盒測試

Anthropic 指出 agent 的自主性會帶來較高成本與錯誤累積的風險，因此建議在沙盒中大量測試並加上護欄 [S1.8]。

## 5. 生成與評估分離

evaluator-optimizer 讓一個 LLM 生成、另一個評估並回饋 [S1.4]。

## ⚠ 檢查者本身也可能出錯

ChemCrow 案例中，LLM 自我評估認為兩個系統表現相近，專家人工評估卻發現其中之一大幅領先，作者因此提醒：在需要深度專業的領域，用 LLM 評估自己可能有問題 [S3.9]。所以「檢查」最好至少包含一個不靠同一個模型判斷的依據，例如規則、原始來源比對或人工抽查（這句是本專案的推論，不是來源直接結論）。

相關：[agent-loop](agent-loop.md)、[tools](tools.md)。
