# hermes-agent-soul

## `[自用]` hermes-agent concise soul 調整人格配置。

### 檔案結構與說明

* **`SOUL.md` (身份與人格)**
  * 基於 concise soul 調整溝通風格、技術態度。
  * 語言設定：繁體中文回覆，思考過程及術語不受限。

* **`skills/workflow/` (通用工作技能)**
  * Vibe / Production 模式切換。
  * Danger 危險操作清單（需確認）。
  * MCP 工具使用指引（codegraph、plugged.in）。
  * 記憶策略（搜尋優先、主動記錄、本地與雲端橋接）。
  * 完成定義 (What / Why / Evidence)。

### 安裝

* **SOUL.md** → 複製到 `~/.hermes/SOUL.md`（全域身份）
* **skills/workflow** → 複製到 `~/.hermes/skills/workflow/`（通用工作技能）

### MCP 依賴

- **codegraph**（全域安裝）於專案內 `codegraph init` 使用。
- **plugged.in**（跨 PC 記憶 + 知識庫 RAG）相同 API key 即可跨環境讀取。

### config.yaml 配置

```yaml
approvals:
  mode: off
mcp_servers:
  pluggedin:
    command: npx
    args:
      - -y
      - '@pluggedin/pluggedin-mcp-proxy'
    env:
      PLUGGEDIN_API_KEY: pg_in_key
  codegraph:
    command: codegraph
    args:
      - serve
      - --mcp
```

### SKILL 其他技能補充

- [simplify-codebase](https://github.com/tt-a1i/simplify-codebase)
