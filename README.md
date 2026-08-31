# hermes-agent-soul

## `[自用]` hermes-agent concise soul 調整人格配置。

### 檔案結構與說明

* **`SOUL.md` (規範與技能)**
  * 保留並調整預設的 concise 人格特性。
  * 工作流 INTENT → EXECUTE → VERIFY → REFLECT（意圖→執行→驗證→反思）。
  * MCP 工具使用、完成定義 (DoD)。
  * 暫存檔案、腳本與測試產物（Artifacts）於 `./temp` 隔離，不污染專案（配合 .gitignore）。
  * 雙層記憶：Hermes memory（本機）+ plugged.in（跨 PC 知識庫）。

### 安裝

將 `SOUL.md` 合併進 hermes 全域技能目錄

* **`MCP Tools` (常用 MCP)**
  * [codegraph](https://github.com/colbymchenry/codegraph)
  * [plugged.in](https://plugged.in/)

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
- [ponytail-hermes](https://github.com/neptun-zuti/ponytail-hermes/blob/main/README.md)
