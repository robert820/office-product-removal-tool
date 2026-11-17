<div align="center">

<a href="https://blog.dei3c.com" target="_blank" rel="noopener noreferrer">
  <img src="https://github.com/user-attachments/assets/2830eb70-512c-4ddb-87ec-5213a6e465b1" alt="得翼科技 | Office Product Removal Tool" height="70" />
</a>

<br /><br />

[繁體中文](../../README.md) · [简体中文](README_zh-CN.md) · **English**

# Office Product Removal Tool

### Read-only inventory of Microsoft 365 / Office, Project and Visio

[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-blue?style=flat-square)](https://github.com/robert820/office-product-removal-tool)
[![License](https://img.shields.io/badge/License-Freeware-informational?style=flat-square)](../../LICENSE)
[![Status](https://img.shields.io/badge/Status-In%20Development-orange?style=flat-square)](#-current-status)

</div>

---

## 📖 Overview

Want to know which Microsoft 365, Office, Project or Visio products are installed? **Office Product Removal Tool** provides a read-only inventory on the Windows desktop and the command line, scanning the Click-to-Run configuration and the 32/64-bit uninstall registry.

Please note: the current build only inventories products and **does not implement removal**; `--remove` and `--apply` report an error and refuse to run.

---

## 📌 Current status

> In development (0.1.0). **Read-only inventory only**; removal is not implemented and no downloadable build has been released yet.

---

## ✨ Features

### 1. 🔎 Click-to-Run product data
- Reads the product ID, version and platform fields available in the Office Click-to-Run configuration as inventory leads.

### 2. 🧾 32/64-bit uninstall-registry scan
- Lists the Office, Project and Visio uninstall entries registered in the Windows registry.

### 3. 🪟 GUI and command line
- View results in the desktop GUI; the CLI supports `--scan`, `--json` and `--help`. The UI language defaults to Traditional Chinese or English based on the Windows display language and can be switched manually.

### 4. 🛡️ Strictly read-only scanning
- Only product registry information is read; no removal is started, Office is not closed and arbitrary UninstallString values are never executed.

---

## 💻 Scope & limitations

| Item | Status | Notes |
| :--- | :--- | :--- |
| Click-to-Run Office | Read-only inventory implemented | Does not mean every product can be removed individually |
| MSI Office / Project / Visio | Read-only registry scan implemented | Removal is not performed |
| Microsoft Store / Appx | Not implemented | Store / Appx packages are neither inventoried nor removed |
| Product removal | Not implemented | `--remove` and `--apply` report an error and refuse to run |
| Windows version | Targets Windows 10 / 11 | No Windows 7 support is claimed; a successful build does not prove OS compatibility |

---

## 🚀 Workflow

1. Open the GUI, or run the CLI with `--help` to see the available options.
2. Run the read-only scan (CLI: `--scan`) to list the products found in the Click-to-Run configuration and the uninstall registry.
3. Use `--json` for machine-readable output; treat the result as registry inventory, not as a full licensing or installation-state verdict.
4. The tool does not uninstall any Office product; follow Microsoft's official support procedure if removal is needed.

---

## 📦 Download

No downloadable build has been released yet. Once released, it will be provided on the [Releases page](https://github.com/robert820/office-product-removal-tool/releases).

---

## 🖥️ Requirements

- **OS**: Windows 10 / 11
- **Privileges**: the read-only scan does not modify the system
- **Runtime**: native Rust executable; no .NET or VC++ redistributable required

---

## ❓ FAQ

<details>
<summary><b>Can it remove Office, Project or Visio for me?</b></summary>

Not at the moment. Only the read-only inventory exists; removal is not implemented and the related options refuse to run.

</details>

<details>
<summary><b>If several products are found, can I remove them one by one?</b></summary>

No. A shared Click-to-Run installation can contain several product IDs, and Microsoft's Get Help Office removal workflow operates on an Office version scope, not on a single product ID.

</details>

<details>
<summary><b>Does it support Windows 7?</b></summary>

The target is Windows 10 / 11. No Windows 7 support or full runtime validation is claimed.

</details>

---

## 💬 Feedback & support

- 🐛 **Bug reports & feature requests**: please use the [Issues page](https://github.com/robert820/office-product-removal-tool/issues).
- 🌐 **DEI Tech official website**: [https://blog.dei3c.com](https://blog.dei3c.com)
- 📧 **Support & business inquiries**: please contact us through the official website.

---

## 📄 License

This software is released under a Proprietary Freeware license. See the [LICENSE](../../LICENSE) file for the full terms and disclaimers.

- Third-party components: this software uses Slint (Royalty-Free License) and several open-source Rust crates; see [THIRD_PARTY_NOTICES.md](../../THIRD_PARTY_NOTICES.md) for the notices.

<a href="https://slint.dev"><picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/slint-ui/slint/master/logo/MadeWithSlint-logo-dark.png">
  <img src="https://raw.githubusercontent.com/slint-ui/slint/master/logo/MadeWithSlint-logo-light.png" alt="Made with Slint" width="160">
</picture></a>
