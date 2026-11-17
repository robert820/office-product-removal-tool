<div align="center">

<a href="https://blog.dei3c.com" target="_blank" rel="noopener noreferrer">
  <img src="https://github.com/user-attachments/assets/2830eb70-512c-4ddb-87ec-5213a6e465b1" alt="得翼科技 | Office Product Removal Tool" height="70" />
</a>

<br /><br />

[繁体中文](../../README.md) · **简体中文** · [English](README_en.md)

# Office 产品清单与卸载准备工具

### 唯读盘点 Microsoft 365／Office、Project、Visio

[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-blue?style=flat-square)](https://github.com/robert820/office-product-removal-tool)
[![License](https://img.shields.io/badge/License-Freeware-informational?style=flat-square)](../../LICENSE)
[![Status](https://img.shields.io/badge/Status-In%20Development-orange?style=flat-square)](#-目前状态)

</div>

---

## 📖 软件简介

想整理电脑安装了哪些 Microsoft 365、Office、Project 或 Visio？**「Office Product Removal Tool」** 提供 Windows 桌面与命令行的唯读产品盘点，扫描 Click-to-Run 设置及 32／64 比特卸载登录信息。

请留意：目前版本只负责盘点，**尚未实作卸载**；`--remove` 与 `--apply` 会回报错误并拒绝操作。

---

## 📌 目前状态

> 开发中（0.1.0）。目前**只有唯读盘点**；卸载尚未实作，也尚未发布可下载的运行档。

---

## ✨ 功能介绍

### 1. 🔎 Click-to-Run 产品信息
- 读取 Office Click-to-Run 设置中可取得的产品识别、版本与平台字段，作为盘点线索。

### 2. 🧾 32／64 比特卸载登录扫描
- 整理 Windows 登录中注册的 Office、Project 与 Visio 卸载项目。

### 3. 🪟 图形接口与命令行
- 桌面 GUI 查看结果；CLI 支持 `--scan`、`--json`、`--help`；接口语言会依 Windows 显示语言缺省为繁体中文或英文，可手动切换。

### 4. 🛡️ 扫描期间保持唯读
- 只读取产品登录信息，不启动移除进程、不关闭 Office，也不调用登录中任意的 UninstallString。

---

## 💻 支持范围与限制

| 项目 | 目前状态 | 说明 |
| :--- | :--- | :--- |
| Click-to-Run Office | 唯读盘点已实作 | 不代表每个产品都可独立卸载 |
| MSI Office／Project／Visio | 唯读登录扫描已实作 | 尚未运行移除 |
| Microsoft Store／Appx | 尚未实作 | 目前不盘点、不移除 Store／Appx 套件 |
| 产品卸载 | 尚未实作 | `--remove`、`--apply` 目前会回报错误并拒绝操作 |
| Windows 版本 | 目标 Windows 10／11 | 没有 Windows 7 支持宣称；建置成功不等于 OS 兼容性已验证 |

---

## 🚀 使用流程

1. 打开图形接口，或在命令行使用 `--help` 查看操作方式。
2. 运行唯读扫描（CLI：`--scan`），查看从 Click-to-Run 设置与卸载登录列出的产品。
3. 需要机器可读结果时使用 `--json`；请将结果视为登录盘点信息，而非完整的授权或安装状态判定。
4. 本程序不会卸载任何 Office 产品；如需移除，请依 Microsoft 官方支持流程另行处理。

---

## 📦 下载与使用说明

目前尚未发布可下载的运行档；发布后将提供于本项目的 [Releases 页面](https://github.com/robert820/office-product-removal-tool/releases)。

---

## 🖥️ 系统与环境需求

- **操作系统**：Windows 10 / 11
- **运行权限**：唯读扫描无需修改系统
- **运行环境**：原生 Rust 运行档，无须额外安装 .NET 或 VC++ 可转发套件

---

## ❓ 常见问题 (FAQ)

<details>
<summary><b>这个工具目前可以帮我移除 Office、Project 或 Visio 吗？</b></summary>

目前不行。现阶段只有唯读盘点；移除功能尚未实作，相关参数会拒绝运行。

</details>

<details>
<summary><b>扫描找到多个产品，就代表可以逐一移除吗？</b></summary>

不代表。共用 Click-to-Run 安装可能包含多个产品识别，而 Microsoft Get Help 的 Office 移除流程是以 Office 版本范围操作，并非单一产品 ID 移除。

</details>

<details>
<summary><b>支持 Windows 7 吗？</b></summary>

目前以 Windows 10／11 为目标，尚无 Windows 7 支持宣称或完整运行验证。

</details>

---

## 💬 问题反馈与支持

- 🐛 **错误回报与功能建议**：欢迎至本项目的 [Issues 页面](https://github.com/robert820/office-product-removal-tool/issues) 提出。
- 🌐 **得翼科技官方网站**：[https://blog.dei3c.com](https://blog.dei3c.com)
- 📧 **技术支持与商务洽询**：请通过官方网站联系我们。

---

## 📄 授权条款 (License)

本软件采用专有免费软件授权（Proprietary Freeware），完整授权规范、使用条款与免责声明请参阅 [LICENSE](../../LICENSE) 文件。

- 第三方组件：本软件使用 Slint（Royalty-Free License）与多个开源 Rust 套件，授权声明请见 [THIRD_PARTY_NOTICES.md](../../THIRD_PARTY_NOTICES.md)。

<a href="https://slint.dev"><picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/slint-ui/slint/master/logo/MadeWithSlint-logo-dark.png">
  <img src="https://raw.githubusercontent.com/slint-ui/slint/master/logo/MadeWithSlint-logo-light.png" alt="Made with Slint" width="160">
</picture></a>
