# Second Brain Kit 中文說明

這是一組可以重複使用的 AI Agent Skills，用來建立一個以 GitHub 同步、相容 Obsidian，並且能讓人與不同 AI Agent 共用的 Second Brain。

這套結構的核心不是收集越多筆記越好，而是把「還沒處理的資料、外部來源、整理後的知識、專案應用與輸出」分開管理，同時保留它們之間的關聯。

## 目前提供的 Skills

### setup-second-brain

建立新的 GitHub-backed Second Brain，包括 Folder Structure、AGENTS.md、Schema、Workflow、增量 Weekly Review 與 Note Templates。

未來像是既有 Second Brain 的遷移工具，可以再獨立加入 `skills/`，不需要改動目前的 Setup Skill。

## 結構

```text
00 Inbox/
10 Sources/
20 Knowledge/
30 Projects/
40 Outputs/
90 System/
```

![Second Brain 架構與資料流](./assets/second-brain-architecture.zh-TW.PNG)

- **Inbox**：還沒處理的資料與臨時記錄。
- **Sources**：整理過、值得保留的外部來源與出處。
- **Knowledge**：從 Sources 整理、累積後，可以持續更新與重複使用的知識。
- **Projects**：專案特定的背景、決策，以及 Knowledge 在專案裡的應用。
- **Outputs**：Blog、社群文章、文件或其他準備發布與分享的成果。
- **System**：整套 Second Brain 的 Schema、Workflow、維護規則、Index 與 Log。

## 怎麼使用

在支援 Skills 的 AI Agent 中安裝或載入這個 Repo，然後直接告訴 AI：

> 使用 second-brain-kit 幫我建立一套 Second Brain。

GitHub Repo 是這套架構最基本的共用儲存位置。Setup 時，AI 會先確認要使用哪個 GitHub Repo，並檢查目前的 Agent 是否能透過已驗證的 GitHub 整合、MCP、CLI 或 API 直接讀寫 Repo。如果還沒有 Repo，而 Agent 具備建立 Repo 的能力，可以直接協助建立；只有在需要時才提供手動建立 GitHub Repo 的指引，不會預設把 GitHub 基礎教學塞進流程。

Second Brain 很可能包含個人筆記、專案內容與尚未公開的資料，因此**強烈建議使用 Private Repo**。Setup Skill 會先檢查 Repo 的 visibility，如果是 Public，會在寫入資料前提醒你，並在需要時協助改成 Private。

確認 GitHub 可以直接存取後，AI 才會建立 Folder Structure、`AGENTS.md`、Schema、Workflow 與維護規則。本機 Obsidian Vault 是選配，需要時再把同一個 Repo clone 到指定資料夾即可。

如果使用的 Agent 沒有 Skill 安裝機制，也可以直接把這個 GitHub Repo 提供給 AI，請它讀取並按照 `skills/setup-second-brain/SKILL.md` 完成初始化。

## 為什麼使用 GitHub

筆記本身仍然是一般 Markdown，也可以直接作為 Obsidian Vault 使用。GitHub 負責讓不同電腦與能存取 GitHub 的 AI 工具共用同一份資料。

因此上層使用的工具可以更換，不管是 Obsidian、Coding Agent、ChatGPT 或其他工具，都不需要各自維護一份獨立的知識庫。

## 定期整理

Second Brain 不應該每次整理時都重新讀取所有 Sources。

Source 會記錄是否已經整理過，正常的 Weekly Review 只處理最近新增或還沒有整理的 Sources，再更新受到影響的 Knowledge。已經整理過的 Sources，只有在新的資料可能改變原本理解時才需要重新讀取。

這樣 Sources 可以持續累積，而 Knowledge 也會隨著新的資料持續更新。

## Repo 內容

- `skills/setup-second-brain/SKILL.md`：AI Agent 建立與維護 Second Brain 時使用的主要 Skill。
- `skills/setup-second-brain/templates/AGENTS.md`：初始化後提供給 AI Agent 的操作規則。
- `skills/setup-second-brain/templates/schema.md`：Source、Knowledge 等資料的 metadata 與 lifecycle。
- `skills/setup-second-brain/templates/workflows.md`：Capture、Source ingestion、Output、Git synchronization 等流程。
- `skills/setup-second-brain/templates/weekly-knowledge-review.md`：每週增量整理 Sources → Knowledge 的規則。
- `skills/setup-second-brain/templates/source.md`：Source Note 範本。
- `skills/setup-second-brain/templates/knowledge.md`：Knowledge Note 範本。

## 設計原則

這套 Second Brain 的目的不是把所有東西都存下來，而是保留可以追查的 Sources，把真正有用的內容整理成可以持續更新的 Knowledge，並讓人和 AI Agent 都能使用同一份資料。

整體結構刻意維持簡單，有實際需求時再往上增加，不需要一開始就建立一套很複雜的知識管理系統。
