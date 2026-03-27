# Repository Guidelines

## Project Structure & Module Organization
- `src/`：核心 TypeScript 程式（主 CLI 與入口）。
  - `src/index.ts`：主要匯出邏輯（參數、抓取、輸出、附件）。
  - `src/cli.ts`：CLI 入口。
- `tests/`：Bun 測試，當前主要為 `tests/index.spec.ts`。
- `scripts/`：維運腳本（版本 bump、建置後修補、seed publish）。
- `dist/`：`bun build` 產生的發布輸出（`dist/index.js`, `dist/cli.js`）。
- `docs/`：發布、PRD、release 自動化與 troubleshooting 文件。

## Build, Test, and Development Commands
- `bun run start`：本地啟動 CLI。
- `bun run help`：顯示 CLI 用法。
- `bun run check`：`bun --check` 語法檢查。
- `bun run test`：執行單元測試。
- `bun run build`：建立 `dist/` 發布檔。
- `bun run bump`：將 `package.json` 版本 patch +1。
- `bun run publish:seed`：第一次手動發佈初始化腳本。

## Coding Style & Naming Conventions
- TypeScript + ESM（`package.json` 的 `type: module`）。
- 2 空格縮排、`camelCase` 變數/函式、`PascalCase` 型別。
- 優先單一職責函式，CLI 參數解析與 I/O 分離。
- 無外部依賴原則（可接受現有 Node/Bun 內建 API）。
- 目前無額外 lint pipeline，請維持 `bun run check` + 測試通過。

## Testing Guidelines
- 測試框架：`bun:test`。
- 以行為為主：參數解析、URL 驗證、附件處理、下載與替換邏輯。
- 測試位置：`tests/*.spec.ts`。
- 提交前請至少跑：
  - `bun run check`
  - `bun run test`

## Commit & Pull Request Guidelines
- Commit 風格建議：`feat:`, `fix:`, `docs:`, `chore:`（本專案已有此格式）。
- PR 需說明：變更範圍、影響檔案、驗證指令與結果。
- 涉及發佈流程時，需提及 workflow 影響與可回滾步驟。
- 更新 docs 時同步更新 `README.md` / `docs/` 相關章節。

## Security & Release Notes
- 執行前需確認 `gh auth status` 可用（CLI 依賴）。
- 發佈文件位於：
  - `docs/NPM_TRUSTED_PUBLISHING.md`
  - `docs/RELEASE_AUTOMATION.md`
  - `docs/SEED_PUBLISH_MECHANISM.md`

## Session Experience Notes (2026-03-27)
- 已修正 `npx` 安裝版與全域安裝版 `--help` 顯示差異（預設改為 `--help` 動態命令）：  
  - npx 環境顯示 `npx @willh/github-issues-exporter`
  - 全域安裝環境顯示 `github-issues-exporter`
- 已新增 `--version` / `-v`，與套件 `vX.Y.Z` 版本輸出整合，並加入回歸測試。
- 文件全面同步（`README.md`、`CHANGELOG.md`、`docs/PRD.md`、`docs/NPM_TRUSTED_PUBLISHING.md`）以避免舊用法殘留。
- 遇到 CI/發佈常見問題時的處置：
  - `workflow` YAML parse error、`shellcheck` heredoc 相容性、Node 版本相依問題，已在 workflow 調整中修正。
  - `npm publish` Trusted Publishing `422 provenance`，已補齊 `package.json` 的 `repository.url` 及 release 流程一致性。
  - `ETARGET`/版本不存在問題透過核對 registry version、npx 版本參數與 lock定命令解法處理。
