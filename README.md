# Update Arduino and Libraries

Codex Skill for refreshing an existing Windows Arduino installation bundle, including official installers, Arduino CLI, ESP32 Core, libraries, scripts, manifests, checksums, and user documentation.

## 中文說明

這是用來更新 Windows Arduino 安裝套件的 Codex Skill。當你說「更新 Arduino 及程式庫」時，它會先檢查既有安裝資料夾與版本，再依 Arduino、Espressif 及程式庫維護者的官方來源，整理需要更新的安裝檔、ESP32 Core、程式庫、腳本、版本清單與 SHA-256 校驗清單。

### 使用方式

在 Codex 中說「更新 Arduino 及程式庫」，並可附上要更新的資料夾路徑或雲端硬碟位置。若未提供位置，Skill 會先檢查目前專案，再於 Windows 已掛載的使用者資料磁碟中尋找可辨識的 `Arduino安裝` 資料夾；若找到多個可能目標，會先請你指定。

### 更新內容

- 比對 Arduino IDE、Arduino CLI、ESP32 Core 與已列出的 Libraries 版本。
- 從官方來源下載缺少或過期的材料，記錄來源，並在官方提供校驗碼時進行驗證。
- 同步更新安裝腳本、`manifest.json`、`SHA256SUMS.txt`、README 與驗證文件。
- 檢查批次檔換行格式、腳本引用路徑、檔案完整性與版本資訊是否一致。
- 回報實際完成的下載與檢查，以及尚待人工確認的項目。

### 安全界線

此 Skill 只準備及檢查安裝套件，不會自行啟動安裝程式、要求管理員權限、安裝軟體或更改系統設定。它不會猜測開發板型號、FQBN、GPIO、USB 模式或 COM Port；未實際驗證的電腦與硬體狀態會標示為待確認。

### 檔案與版本

技能指示位於 `SKILL.md`，Codex 顯示設定位於 `agents/openai.yaml`，目前版本記錄在 `VERSION`。本 Repo 採用語意化版本；版本檔、技能 metadata 與 Git tag 應保持一致。

---

## English

## Version

Current version: **1.0.0** (`VERSION`; Git tag `v1.0.0`).

## Use

Invoke the skill by asking Codex: **“Update Arduino and Libraries”** or **「更新 Arduino 及程式庫」**. Provide a folder path or cloud-drive location when you want to target a specific bundle. Otherwise, the skill searches the current project and, when needed on Windows, mounted user data drives for a uniquely identifiable `Arduino安裝` bundle.

The skill inspects the existing manifest, checksum list, documentation, scripts, and package files before updating. It checks official vendor sources, updates missing or outdated materials, aligns version and checksum metadata, and reports validation results and any remaining manual steps.

## Safety boundaries

- Prepares the installation bundle; it does not launch installers, elevate privileges, install software, or change system settings.
- Uses official vendor and maintainer sources and records source URLs.
- Preserves unrelated files and avoids guessing board-specific settings such as FQBN, GPIO, USB mode, or COM port.
- Marks hardware and target-computer checks as pending unless they were actually performed.

## Files

- `SKILL.md` — skill instructions and operating boundaries.
- `agents/openai.yaml` — Codex display name and invocation prompt.
- `VERSION` — current semantic version.

## Versioning

Versions use Semantic Versioning. The `VERSION` file, `SKILL.md` metadata, and Git release tag should agree. Use patch versions for compatible instruction fixes, minor versions for backward-compatible workflow additions, and major versions for incompatible behavior or boundary changes.
