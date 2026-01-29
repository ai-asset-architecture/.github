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
python3 -m pip install "git+https://github.com/ai-asset-architecture/aaa-tools.git@v0.7.1"
aaa --version
```

**3) 下載計畫檔並啟動**
```bash
gh api -H "Accept: application/vnd.github.v3.raw" \
  /repos/ai-asset-architecture/aaa-tools/contents/runbooks/init/plan.v0.7.json?ref=v0.7.1 \
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

目前已完成 AAA v0.1 → v1.1，重點里程碑如下（由新到舊）：

- **v1.6**：Multi-Agent Orchestration 完成 (2026-01-29)；Agent 衝突解決、TTL File Locking、CLI Lock Commands。
- **v1.5**：Self-Healing Engine 完成 (2026-01-29)；Gate 失敗自動修復、語義檢查、修復 PR 自動產生。
- **v1.4**：Guardian Daemon 完成 (2026-01-28)；Policy Distribution、Registry-based Ops、`aaa check --remote`。
- **v1.3**：Governance Compiler 完成 (2026-01-28)；自然語言定義政策自動編譯、互動式選單。
- **v1.2**：Semantic Registry 完成 (2026-01-28)；版本握手、語義查詢、Object-centric 治理。
- **v1.1**：AI-Native Interface 完成 (2026-01-28)；CLI 支援 AI-first 協定、語義化錯誤訊息、MCP 實驗整合。
- **v1.0**：Gate-First Enterprise Governance；ruleset + governance-gate 強制合規，enterprise bootstrap 與 release integrity 落地。  
- **v0.9**：治理 KPI 與合規儀表板落地；新增 drift/repo health 指標與 post-mortem 發佈機制。  
- **v0.8**：Marketplace Assets 完成；Pack Registry / Manifest / 安裝與 pack checks 可插拔化。  
- **v0.7**：SSOT checks 與 repo_type 持久化落地；verify-ci 與 repo-checks 行為一致化。  
- **v0.6**：Agent safety 邊界與安全測試基線完成（scope/path traversal 防護）。  
- **v0.5**：Runbook runtime 與標準 action library 成形，upgrade/audit runbooks 補齊。  
- **v0.4**：SOP 與 CLI 合約對齊，加入 post-init audit 閉環。  
- **v0.3**：onboarding 文件一致性與 CI 穩定治理上線。  
- **v0.2**：決策樹與可治理/可路由/可降級架構建立。  
- **v0.1**：可執行架構基線與治理規範完成。  

詳細里程碑與版本紀錄請見 `aaa-tpl-docs/reports/`（內部）。

**v1.6 對外摘要與證據**
- Architecture: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/milestones/20260129_v1.6_Multi_Agent_Orchestration.md
- Completion report: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v1.6_completion_report_20260129.md

**v1.5 對外摘要與證據**
- Architecture: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/milestones/20260128_v1.5_Self_Healing_Engine.md
- Completion report: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v1.5_completion_report_20260128.md

**v1.4 對外摘要與證據**
- Architecture: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/milestones/20260128_v1.4_Policy_Distribution.md
- Completion report: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v1.4_completion_report_20260128.md

**v1.3 對外摘要與證據**
- Architecture: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/milestones/20260128_v1.3_Governance_Compiler.md
- Completion report: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v1.3_completion_report_20260128.md

**v1.2 對外摘要與證據**
- Architecture: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/milestones/20260128_v1.2_semantic_registry.md
- Completion report: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v1.2_completion_report_20260128.md

**v1.1 對外摘要與證據**
- Architecture: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/milestones/20260128_v1.1_semantic_era.md
- Completion report: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v1.1_completion_report_20260128.md

**v1.0 對外摘要與證據**
- Completion report: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v1.0_completion_report_20260124.md

**v0.9 對外摘要與證據**
- One-pager: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v0.9_one_pager_20260123.md
- Gate evidence: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v0.9_gate_evidence_20260123.md
- Completion report: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v0.9_completion_report_20260123.md
- Observability upgrade: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v0.9_observability_upgrade_20260124.md

**歷史完成報告（摘要）**
- v0.8: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v0.8_completion_report_20260124.md
- v0.7: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v0.7_completion_report_20260123_0915.md
- v0.6: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v0.6_completion_report_20260122_2300.md
- v0.5: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v0.5_completion_report_20260121_2348.md
- v0.5 upgrade/audit runbooks: https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/milestones/completion-reports/aaa_v0.5_upgrade_audit_runbooks_20260124.md

**待辦紀錄（Pending Logs）**
- ✅ [COMPLETED 2026-01-28] Nightly 驗證：確認 P2-1 threshold 失敗仍可發布 dashboard  
  - Evidence: [P2-1 Resilience Validation](https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/audits/2026-01-28-p2-1-nightly-resilience-validation.md)
- ✅ [COMPLETED 2026-01-28] P0-3 證據補齊：實跑 `aaa audit --local` 並更新稽核報告  
  - Evidence: [Governance Suite Report](https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/audits/2026-01-28-governance-suite-evidence.md) | [JSON](https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/audits/2026-01-28-governance-suite-evidence.json)
- ✅ [COMPLETED 2026-01-28] P2-3 後續驗證：repo-upgrade / repo-audit workflow 實際證據  
  - Evidence: [Workflow Execution Report](https://github.com/ai-asset-architecture/aaa-tpl-docs/blob/main/internal/development/audits/2026-01-28-workflow-evidence.md) | [Run #21417181000](https://github.com/ai-asset-architecture/aaa-actions/actions/runs/21417181000) | [Run #21417186520](https://github.com/ai-asset-architecture/aaa-actions/actions/runs/21417186520)  

### 🧭 未來 Roadmap（Future）

接下來版本規劃（由近到遠）：

- **v1.6**：Multi-Agent Orchestration 完成 (2026-01-29)；Agent 衝突解決、TTL File Locking、CLI Lock Commands。
- **v1.5**：Self-Healing Engine 完成 (2026-01-29)；Gate 失敗自動修復、語義檢查、修復 PR 自動產生。
- **v1.4**：Guardian Daemon 完成 (2026-01-28)；Policy Distribution、Registry-based Ops、`aaa check --remote`。
- **v1.3**：Governance Compiler 完成 (2026-01-28)；自然語言定義政策自動編譯、互動式選單。
- **v1.2**：Semantic Registry 完成 (2026-01-28)；版本握手、語義查詢、Object-centric 治理。
- **v1.1**：AI-Native Interface 完成 (2026-01-28)；CLI 支援 AI-first 協定、語義化錯誤訊息、MCP 實驗整合。
- **v1.7 — Federated Governance**：軟體供應鏈治理、Remote audit、跨組織信任鏈
- **v1.8 — Observability 2.0**：治理指標時序化、風險帳本、異常告警與趨勢 Dashboard
- **v1.9 — Supreme Court Interface**：人類最高決策介面、案例法系統、道德兩難仲裁
- **v2.0 — The Agent OS**：完整 Agent 作業系統、生產級 Agent 自主能力、統一治理層  

---

**Last Updated**: 2026-01-29  
**Version**: 1.6  

更多技術落地細節與初始化順序，請看 `.github/README.md`。
