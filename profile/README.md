# 🚀 AI 資產化架構 (AI Asset Architecture, AAA)

**將您的 AI 技能從「高折舊的技巧」轉變為「可複利的系統化資產」。**

---

## 🚦 Start Here（快速開始）

### 對訪客（Visitors）
目前本組織採 **Private Beta** 運作。  
若您希望加入或試用，請聯絡 `@aaa/architect`，或提交 Access Request Issue：  
https://github.com/ai-asset-architecture/.github/issues/new?template=access_request.yml

### 對成員（Members）— 5 分鐘開案
我們採用「零相依啟動」：**不需要 clone 整個 AAA**，只要安裝 CLI。

**1) 準備環境**
```bash
gh --version
gh auth status
gh auth setup-git
git --version
python3 --version
```

**2) 安裝 AAA 工具**
```bash
python3 -m pip install --upgrade pip
python3 -m pip install "git+https://github.com/ai-asset-architecture/aaa-tools.git@v0.2.0"
aaa --version
```

**3) 下載計畫檔並啟動**
```bash
gh api -H "Accept: application/vnd.github.v3.raw" \
  /repos/ai-asset-architecture/aaa-tools/contents/runbooks/init/plan.v0.1.json?ref=v0.2.0 \
  > /tmp/aaa_plan_resolved.json
aaa init --plan /tmp/aaa_plan_resolved.json
```

詳細步驟請看：  
https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/docs/new-project-sop.md

---

## 1. 背景：您正在經歷「AI 技能焦慮」嗎？

在這個 AI 模型快速迭代的時代，許多專業人士正面臨一個核心困境：**技能的快速折舊危機**。您的努力成果，可能正隨著下一個模型版本或工具介面的更新而快速歸零。

| 您的現狀：高折舊技能 (High Depreciation Skills) | 潛在風險 (Risk) |
| :--: | :--: |
| 僅專注於**特定模型的 Prompt 小技巧** | 指令在下一代模型上可能失效，導致努力歸零 (Erasable)。 |
| 過度依賴**熱門工具的 UI 操作細節** | 工具一改版，舊的學習成果就必須重頭開始，產生學習的「清零鍵」。 |
| 追求**一次性的內容生成速度** | 缺乏可複用的標準和流程，每次產出都是從零開始，無法累積價值。 |
| **核心問題：** 努力無法累積。您感覺自己是技能的「租客」(Renter)，而不是資產的「房東」(Owner)。 | **焦慮：** 「我會不會被更強大的 AI 模型取代？」這種不確定性帶來極大的職涯焦慮。 |

---

## 2. 解決方案：AAA 架構的誕生與核心三大支柱

AI 資產化架構（AAA）的目標是建立一套**可重用 (Reusable)、可演進 (Evolvable)、可治理 (Governed)** 的 AI 協作系統。它要求將工作重心從「我懂了什麼工具」轉向「我留下了什麼資產」。

### 2.1 核心洞察：鐵打的評估，流水的模型

AAA 系統的核心哲學是：**模型會不斷流動和更新，但定義品質的標準必須是恆定的錨點。** 透過這套系統，模型更新不再是您的威脅，而是驅動您資產價值增長的「加速器」。

### 2.2 AAA 架構的三大支柱

AAA 系統圍繞三個核心支柱構建，是您「職涯護城河 (Professional Moat)」的基石：

| 支柱 (The Pillar) | 核心概念 | 職能/目標 |
| :--: | :--: | :--: |
| **評估集 (Evals)** | **品質的錨點 (The Anchor)** | 將您對品質的「感覺」轉化為「可驗證的工程標準」，作為 LLM 輸出的單元測試 (Unit Tests)。 |
| **流程劇本 (Playbook)** | **系統化的流程 (The Flow)** | 將隨機的 AI 對話轉化為 SOP，實現流程與 AI 模型解耦 (Decoupling)。 |
| **責任閉環 (Accountability)** | **不可壓縮的人類價值 (The Human)** | 人類負責接軌現實、管理風險、進行價值取捨，並為最終交付結果負責。 |

### 2.3 核心資產與工程化工具箱

我們將上述支柱拆解為四個可程式碼化、可版本控制的核心資產：

| 資產類型 | 實體化內容範例 | 治理方式 |
| :--: | :--: | :--: |
| **Evals** | `test_cases.md`、`passing_criteria.md`、`failure_modes.md` | **SemVer：** 版本控制的是**品質標準**，而非模型。 |
| **Playbooks** | 標準工作流 SOP 文件，包含原子化步驟。 | **Decoupling：** 流程結構穩定，可搭配不同模型。 |
| **Templates** | 模組化提示詞、PRD/API 結構模板。 | **三維標籤：** `#Context_#Format_#Stage` 命名法。 |
| **Artifacts/Tooling** | **AAA CLI**、自動化腳本、JSON Schema 規則庫。 | **Governance as Code：** 將規則變成可執行程式。 |

### 2.4 執行引擎：AAA CLI 的角色

AAA CLI（`aaa-tools`）是關鍵執行引擎，實現 **確定性 (Determinism)** 與 **冪等性 (Idempotent)**，確保新專案啟動、資產同步、治理評測皆可稽核。它透過 `aaa init --plan` 實現從規格到驗證的完整自動化閉環。

---

## 3. AAA 的真正意義：從競速者到系統整合者

在 AI Agents 逐漸成熟的時代，單純追求 **Prompt Engineering** 已是高折舊的競速策略。AAA 提供價值重構的路徑：

| 舊角色：競速者 (The Racer) | 新角色：系統整合者 (The Integrator) |
| :--: | :--: |
| 專注於**輸出速度**與**單次產出** | 專注於**系統結構**與**資產累積** |
| 技能依賴於**模型**的最新版本 | 價值根植於**Evals** 與 **Playbook** 的穩定性 |
| 工作是**執行**任務 | 工作是**整合** Agents 並**承擔最終責任** |
| 容易產生**焦慮感** | 擁有對工作系統的**掌控感** |

**AAA 架構的最終意義在於：**

> **「不要在速度上競爭，要在你留下的『可複用資產』上競爭。」**

將您的核心洞察、品質標準與流程透過程式碼固化，就能建立即使模型不斷演進也能持續增值的專業資產。

---

### ✅ 目前進度（Real Progress）

目前已完成 AAA v0.6 的核心落地，重點進度如下：

- **治理基線**：Branch Protection / CODEOWNERS / Governance 規範已建立
- **工具鏈**：`aaa-tools` CLI + Runbooks/Schema/Contracts 完整對齊，支援 `--json` 與 `--runbook-file`
- **安全治理**：`agent_safety`（預期阻擋視為 PASS）與 `orphaned_assets` 已納入治理檢查
- **技能系統**：skills v0.2（Routing / Rules / Fallback）與 smoke 檢查已上線
- **模板與 SOP**：新專案 SOP（Member Edition）與 AAA 模板已更新
- **Readiness Gate**：v0.6 Gate 規範已形成（內部報告）

詳細里程碑與版本紀錄請見 `aaa-tpl-docs/reports/`（內部）。

### 🧭 近期規劃（Short-Term）

接下來 2–4 週的重點工作：

- **Readiness Gate 自動化**：將 v0.6 Gate 檢查落到可重複驗證流程
- **RDR 可稽核化**：補齊 Route Decision Record（可追溯路由決策）
- **Triage Taxonomy**：建立任務分類與最小測試集
- **技能測試升級**：從 smoke 走向功能級驗證與 fallback 測試

---

更多技術落地細節與初始化順序，請看 `.github/README.md`。
