---
type: knowledge
created: 2026-11-05
updated: 2026-11-05
status: active
tags: [ai-agent, proactive-agent, second-brain, architecture, hitl, autonomy-levels]
projects: []
---

# 主動式超級智能 Agent 架構

**來源**：@Barret_China X 貼文（2026/11/05）— 睡前給 AI 的完整提示詞，醒來驗收成果

## Overview

目標是打造一個能長期在背景運行的本地超級智能系統，讓它主動感知資訊、理解個人上下文、自主發現並推進任務、交付真實成果。使用者只需關注目標與關鍵決策，其餘盡可能交給 AI。

核心意象：「睡前布置作業 → 多源主動感知 → AI 自主分級執行 → HITL 網關把關 → 醒來驗收成果」的一人公司自運轉飛輪。

## Key ideas

### 1. 多源主動感知（Patrol）
- 定時巡檢訊息、郵件、日曆、文件、程式碼倉庫、專案任務。
- 結合個人工作上下文，判斷目前在做什麼、關注什麼、有哪些未完成事項、哪些值得主動推進。
- **工程關鍵**：每個資訊源存 `last_seen_id`（或 commit sha），只處理增量；事項用冪等 hash 去重，避免 Inbox 充滿重複。

### 2. 統一任務中心（Inbox）
- 參考類似 Multica 的方案，在本地建統一任務中心。
- 把發現的待辦、潛在問題、專案機會、需決策事項全部歸入 Inbox。
- 自動分類並判定自主執行等級。

### 3. 自主執行等級（L1–L5）

| 等級 | 能力描述 |
|------|----------|
| L1 | 理解與整理資訊、提取待辦、總結背景 |
| L2 | 分析問題、提供建議與執行方案 |
| L3 | 完成部分工作、生成可交付的中間成果 |
| L4 | 自主完成大部分工作，關鍵環節需人工確認 |
| L5 | 端到端完成任務、自主驗證結果並交付 |

系統依任務類型、上下文、工具能力與權限，自動判斷可推進程度。

### 4. HITL 人機協作網關（Outbox）
- 重要決策、對外溝通、內容發布、敏感操作 → 進入 Outbox。
- 主動推送通知，附帶背景、建議與可執行選項。
- 獲得授權後才繼續執行。
- 這是防止幻覺自循環與失控的安全底座。

### 5. 多 Agent 協作與執行
- 用高能力編碼 Agent（如 Codex）做系統性架構設計與任務拆分。
- 複雜任務自動拆成子任務，交給不同 Agent 並行處理，並管理依賴。
- 執行過程必須落地：真正調用工具、寫必要程式碼、做真實環境整合、測試與驗證，不能只停在設計或 Demo。

### 6. 穩定性與可觀測性
- 任務持久化、異常恢復、失敗重試、權限隔離、資料安全、成本與資源管理。
- 監控看板：Inbox / Outbox、任務狀態、Agent 進度、工具呼叫紀錄、執行日誌、異常、最終交付成果。
- 支援除錯、重試、人工干預、歷史回溯。

### 7. 個人上下文持續更新
- 工作職責、進行中專案、長期目標、技術興趣、日常習慣、個人偏好。
- 讓 Agent 能據此判斷優先級並發現潛在工作機會。

## Practical implications

1. 整個建設過程盡可能自主：調研 → 架構設計 → 任務拆分 → 並行開發 → 整合測試 → 部署運行。
2. 只有真正需要決策或授權的事才找人。
3. 建完後必須用真實任務做端到端自測，驗證「資訊發現 → 任務識別 → 自動規劃 → 自主執行 → 人工確認 → 成果交付」的完整閉環。
4. 架構要清晰、簡潔、可移植、穩定。優先復用現有開源生態（Pi、DSH、Super-Agent、CLI、MCP、Skills、瀏覽器自動化等）。

## Related concepts

- Second Brain / PKM（本 Repo 本身）
- Human-in-the-Loop (HITL)
- Multi-Agent Systems
- Tool-using Agents / MCP
- Incremental processing & idempotency

## Relevant projects

- 未來可應用於本機主動式 Agent 系統建置
- 可與 second-brain-kit 的 Workflow 結合，讓 Agent 主動維護 Knowledge

## Sources

- @Barret_China X 貼文 (https://x.com/Barret_China/status/2118146941217599841)
