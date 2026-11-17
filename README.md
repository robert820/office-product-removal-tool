<div align="center">

<a href="https://blog.dei3c.com" target="_blank" rel="noopener noreferrer">
  <img src="https://github.com/user-attachments/assets/2830eb70-512c-4ddb-87ec-5213a6e465b1" alt="得翼科技 | Office Product Removal Tool" height="70" />
</a>

<br /><br />

**繁體中文** · [简体中文](docs/readme/README_zh-CN.md) · [English](docs/readme/README_en.md)

# Office 產品清單與解除安裝準備工具

### 唯讀盤點 Microsoft 365／Office、Project、Visio

[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-blue?style=flat-square)](https://github.com/robert820/office-product-removal-tool)
[![License](https://img.shields.io/badge/License-Freeware-informational?style=flat-square)](LICENSE)
[![Status](https://img.shields.io/badge/Status-In%20Development-orange?style=flat-square)](#-目前狀態)

</div>

---

## 📖 軟體簡介

想整理電腦安裝了哪些 Microsoft 365、Office、Project 或 Visio？**「Office Product Removal Tool」** 提供 Windows 桌面與命令列的唯讀產品盤點，掃描 Click-to-Run 設定及 32／64 位元解除安裝登錄資訊。

請留意：目前版本只負責盤點，**尚未實作解除安裝**；`--remove` 與 `--apply` 會回報錯誤並拒絕操作。

---

## 📌 目前狀態

> 開發中（0.1.0）。目前**只有唯讀盤點**；解除安裝尚未實作，也尚未發布可下載的執行檔。

---

## ✨ 功能介紹

### 1. 🔎 Click-to-Run 產品資訊
- 讀取 Office Click-to-Run 設定中可取得的產品識別、版本與平台欄位，作為盤點線索。

### 2. 🧾 32／64 位元解除安裝登錄掃描
- 整理 Windows 登錄中註冊的 Office、Project 與 Visio 解除安裝項目。

### 3. 🪟 圖形介面與命令列
- 桌面 GUI 檢視結果；CLI 支援 `--scan`、`--json`、`--help`；介面語言會依 Windows 顯示語言預設為繁體中文或英文，可手動切換。

### 4. 🛡️ 掃描期間保持唯讀
- 只讀取產品登錄資訊，不啟動移除程序、不關閉 Office，也不呼叫登錄中任意的 UninstallString。

---

## 💻 支援範圍與限制

| 項目 | 目前狀態 | 說明 |
| :--- | :--- | :--- |
| Click-to-Run Office | 唯讀盤點已實作 | 不代表每個產品都可獨立解除安裝 |
| MSI Office／Project／Visio | 唯讀登錄掃描已實作 | 尚未執行移除 |
| Microsoft Store／Appx | 尚未實作 | 目前不盤點、不移除 Store／Appx 套件 |
| 產品解除安裝 | 尚未實作 | `--remove`、`--apply` 目前會回報錯誤並拒絕操作 |
| Windows 版本 | 目標 Windows 10／11 | 沒有 Windows 7 支援宣稱；建置成功不等於 OS 相容性已驗證 |

---

## 🚀 使用流程

1. 開啟圖形介面，或在命令列使用 `--help` 查看操作方式。
2. 執行唯讀掃描（CLI：`--scan`），查看從 Click-to-Run 設定與解除安裝登錄列出的產品。
3. 需要機器可讀結果時使用 `--json`；請將結果視為登錄盤點資訊，而非完整的授權或安裝狀態判定。
4. 本程式不會解除安裝任何 Office 產品；如需移除，請依 Microsoft 官方支援流程另行處理。

---

## 📦 下載與使用說明

目前尚未發布可下載的執行檔；發布後將提供於本專案的 [Releases 頁面](https://github.com/robert820/office-product-removal-tool/releases)。

---

## 🖥️ 系統與環境需求

- **作業系統**：Windows 10 / 11
- **執行權限**：唯讀掃描無需修改系統
- **執行環境**：原生 Rust 執行檔，無須額外安裝 .NET 或 VC++ 可轉發套件

---

## ❓ 常見問題 (FAQ)

<details>
<summary><b>這個工具目前可以幫我移除 Office、Project 或 Visio 嗎？</b></summary>

目前不行。現階段只有唯讀盤點；移除功能尚未實作，相關參數會拒絕執行。

</details>

<details>
<summary><b>掃描找到多個產品，就代表可以逐一移除嗎？</b></summary>

不代表。共用 Click-to-Run 安裝可能包含多個產品識別，而 Microsoft Get Help 的 Office 移除流程是以 Office 版本範圍操作，並非單一產品 ID 移除。

</details>

<details>
<summary><b>支援 Windows 7 嗎？</b></summary>

目前以 Windows 10／11 為目標，尚無 Windows 7 支援宣稱或完整執行驗證。

</details>

---

## 💬 問題反饋與支援

- 🐛 **錯誤回報與功能建議**：歡迎至本專案的 [Issues 頁面](https://github.com/robert820/office-product-removal-tool/issues) 提出。
- 🌐 **得翼科技官方網站**：[https://blog.dei3c.com](https://blog.dei3c.com)
- 📧 **技術支援與商務洽詢**：請透過官方網站聯繫我們。

---

## 📄 授權條款 (License)

本軟體採用專有免費軟體授權（Proprietary Freeware），完整授權規範、使用條款與免責聲明請參閱 [LICENSE](LICENSE) 檔案。

- 第三方元件：本軟體使用 Slint（Royalty-Free License）與多個開源 Rust 套件，授權聲明請見 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。

<a href="https://slint.dev"><picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/slint-ui/slint/master/logo/MadeWithSlint-logo-dark.png">
  <img src="https://raw.githubusercontent.com/slint-ui/slint/master/logo/MadeWithSlint-logo-light.png" alt="Made with Slint" width="160">
</picture></a>
