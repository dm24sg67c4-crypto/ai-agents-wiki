# S2｜OpenAI〈A practical guide to building agents〉

- **網址**：https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf
- **來源類型**：原廠實務指南（PDF，約 34 頁）
- **抓取日期**：2026-11-21
- **在 Wiki 中的角色**：定義、運作（元件、迴圈、orchestration）、護欄與檢查

## 要點（引用時請用編號，例如 [S2.3]）

- **S2.1** OpenAI 對 agent 的定義是：獨立代替使用者完成任務的系統。
- **S2.2** 雖然整合了 LLM、但不用它來控制工作流程執行的應用，例如簡單聊天機器人、單輪 LLM、情緒分類器，不算 agent。
- **S2.3** agent 有兩個核心特徵：(1) 用 LLM 管理工作流程執行並做決策，能辨識工作何時完成、主動修正行動，失敗時可中止並把控制權交還使用者；(2) 能使用各種工具與外部系統互動，依流程當前狀態動態選擇工具，並始終在清楚定義的護欄內運作。
- **S2.4** 最值得優先考慮 agent 的場景有三類：複雜決策（例如退款審核）、規則難以維護、大量依賴非結構化資料；若不符合，確定性的解法可能就夠了。
- **S2.5** agent 最基本由三個元件組成：Model（負責推理與決策的 LLM）、Tools（可呼叫的外部函式或 API）、Instructions（規範行為與護欄的明確指示）。
- **S2.6** 工具分三類：Data（取得脈絡資訊）、Action（對系統採取行動，如寄信、更新紀錄）、Orchestration（agent 本身可被當作別的 agent 的工具）。
- **S2.7** 每個 orchestration 方式都有「run」的概念，通常實作成迴圈，讓 agent 持續運作到退出條件成立，常見退出條件包括呼叫最終輸出工具、模型回覆中沒有工具呼叫、發生錯誤、或達到最大回合數。
- **S2.8** 建議先把單一 agent 的能力發揮到極致；需要時再拆成多 agent，兩種常見模式是 Manager（中央 agent 把其他 agent 當工具呼叫）與 Decentralized（agent 之間用 handoff 交棒）。多 agent 系統可以用 graph 建模，agent 是節點，邊是工具呼叫或 handoff。
- **S2.9** 護欄應分層設計：單一護欄通常不夠，要混合多種，包括 relevance classifier、safety classifier、PII filter、moderation、tool safeguards（依風險給低／中／高評級，評估因素包括唯讀或可寫入、能否還原、所需權限與財務影響，並據此觸發自動動作，例如在執行高風險功能前暫停做護欄檢查，或升級給人類）、rules-based protections、output validation。
- **S2.10** 應規劃人類介入機制，兩個主要觸發條件：超過失敗門檻（例如重試太多次）、以及高風險動作（例如大額退款、付款）。
- **S2.11** 選模型的建議流程：先建立 evals 取得基準，用最強模型做原型，再嘗試換成較小的模型看結果是否仍可接受。

## 可信度備註

原廠一手資料，實務性強；程式範例是 OpenAI Agents SDK 專用，概念可通用，細節不一定。
