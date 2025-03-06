<div align="center">

# 🚀 OpenCode for GitHub Copilot Chat

**Use 30+ frontier AI models** (DeepSeek V4, Kimi K3, GLM-5.3, GPT-5.6, Claude Opus 5, Gemini 3.6, Grok 4.6…) in GitHub Copilot Chat. **BYOK**

**Bring Your Own Key (BYOK)** · OpenCode Zen (free + paid models) or Go ($10/mo subscription) · Works with native Copilot Agent Mode

[![CI](https://github.com/ltmoerdani/opencode-copilot-chat/actions/workflows/ci.yml/badge.svg)](https://github.com/ltmoerdani/opencode-copilot-chat/actions/workflows/ci.yml)
[![VS Code Marketplace](https://img.shields.io/badge/Install-VS%20Code%20Marketplace-007ACC?logo=visualstudiocode&logoColor=white)](https://marketplace.visualstudio.com/items?itemName=ltmoerdani.opencode-copilot-chat)
[![Version](https://img.shields.io/github/v/release/ltmoerdani/opencode-copilot-chat?label=Version&color=6c47ff)](https://github.com/ltmoerdani/opencode-copilot-chat/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![VS Code](https://img.shields.io/badge/VS%20Code-1.125%2B-007ACC?logo=visualstudiocode&logoColor=white)](https://code.visualstudio.com/)
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen)](./CONTRIBUTING.md)
[![Stars](https://img.shields.io/github/stars/ltmoerdani/opencode-copilot-chat?style=social)](https://github.com/ltmoerdani/opencode-copilot-chat)

[**✨ Why you'll love it**](#-why-youll-love-it) · [**⚡ Quick Start (60 sec)**](#-quick-start-60-sec) · [**🧠 Models**](#-models) · [**📊 Compare**](#-github-copilot-vs-this-extension) · [**🔧 Settings**](#-settings) · [**❓ FAQ**](#-faq) · [**💬 Community**](#-community)

</div>

---

> **💡 The elevator pitch**
>
> **Copilot Chat is great, but its premium models cost $39/mo (Pro+) and the free tier is rate-limited.**
> This extension plugs **OpenCode's model gateway** into Copilot Chat's model picker. **OpenCode Zen** gives you rotating free models (Big Pickle is currently free; DeepSeek V4 Flash, MiMo-V2.5, and others rotate) plus paid models like Claude Opus, GPT-5.5, and Gemini at pay-as-you-go rates. **OpenCode Go** ($10/mo, $5 first month promo) gives you a curated set of open models (DeepSeek V4 Pro, Kimi K3, GLM-5.3, Qwen3.8 Max, MiMo V2.5 Pro) with generous usage limits. You keep the native Copilot UI, tool-calling, and Agent Mode. You just get **way more models**, often **cheaper than Copilot Pro+**.

---

## 🔥 Why you'll love it

|                                  | What you get                                                                                                                                                                                                                                          |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 💸 **Cheaper than Copilot Pro+** | VS Code + OpenCode **Zen free** models = **$0** for rotating free models (Big Pickle, DeepSeek V4 Flash, MiMo-V2.5, and others). Paid Zen models (Claude Opus, GPT-5.6) available at pay-as-you-go rates. Go subscription **$10/mo** ($5 first month) |
| 🌍 **30+ frontier models**       | DeepSeek V4, Kimi K3, GLM-5.3, Qwen3.8 Max, MiMo V2.5, MiniMax M3, Grok 4.6, Big Pickle, **all in one picker**                                                                                                                                        |
| 🤖 **Full Agent Mode**           | Tool-calling (read files, edit, run terminal) works natively, not just chat. Models also appear in the **Agents window** (Copilot CLI session)                                                                                                        |
| 🧠 **Thinking controls**         | Per-model reasoning effort (DeepSeek `max`, Qwen `thinking_budget`, MiniMax `on/off`, Mimo `low/med/high`)                                                                                                                                            |
| 🖼️ **Vision proxy**              | Text-only models can "see" images via a configured vision model. Per-image descriptions are cached & reused across turns to save quota. Run **OpenCode Go: Configure Vision Proxy** to set it up.                                                     |
| 📊 **Live usage tracking**       | Status bar shows Go subscription burn-rate across 5h / weekly / monthly tiers                                                                                                                                                                         |
| 🔌 **Dual providers**            | OpenCode **Go** ($10/mo subscription) + OpenCode **Zen** (free + paid models). Run both at once, switch instantly                                                                                                                                     |
| 🪫 **Provider on/off**           | Remove or re-add **OpenCode Go** / **OpenCode Zen** from Language Models & every picker anytime; your API keys and BYOK groups are kept, so re-enabling restores everything                                                                           |
| 🎯 **Smart routing**             | Each model family auto-routes to its native transport (`/responses`, `/messages`, `streamGenerateContent`, `/chat/completions`)                                                                                                                       |
| 🖼️ **Vision + PDF + Audio**      | Multimodal models pass through image, PDF, audio, and video inputs. Oversized images auto-resize to 2000×2000 / 5MB to match the gateway contract.                                                                                                    |
| 📐 **Context-size picker**       | Kimi K3 and other tiered-context models expose `256K` vs full-window selection in the per-model configuration, with the cheaper tier selected by default.                                                                                             |
| 🔒 **Your key, your control**    | API key entered once in Language Models → **Add Models…**; stored by VS Code, never leaves your machine                                                                                                                                               |

---

## ⚡ Quick Start (60 sec)

```text
1.  Install or update VS Code 1.125+ ────────────────────────────── ✓
2.  Install this extension ──────────────────────────────────────── ✓
3.  Get an OpenCode Zen API key → opencode.ai/auth ─────────────── ✓
4.  Open Copilot Chat → click model → "Add Models" → OpenCode Zen ── ✓
5.  Paste API key → pick a free model → CHAT 🎉
```

<details>
<summary><b>📖 Detailed step-by-step with screenshots</b></summary>

1. **Install or update [VS Code](https://code.visualstudio.com/)** to version 1.125 or newer. OpenCode BYOK chat works without a GitHub sign-in or Copilot plan.
2. **Install this extension** from the VS Code Marketplace (or press `F5` in this repo for dev mode).
3. **Get an API key:**
   - **Free models:** Sign up at [opencode.ai](https://opencode.ai) → grab an **OpenCode Zen** key. Several models are truly free (Big Pickle, DeepSeek V4 Flash Free, MiMo-V2.5 Free, and others rotate).
   - **Paid Zen models (optional):** Add a payment method to your Zen account to unlock Claude Opus, GPT-5.5, Gemini, and other paid models at pay-as-you-go rates. Adding $20+ balance also improves rate limits on free models.
   - **OpenCode Go (optional):** Subscribe to **OpenCode Go** ($10/mo, $5 first month promo) for curated open models like DeepSeek V4 Pro, Kimi K3, GLM-5.3, Qwen3.8 Max, MiMo V2.5 Pro.
4. **Open Copilot Chat** (Cmd/Ctrl+Shift+I, or click the Copilot icon).
5. **Click the model picker** (current model name) → **Add Models…**
6. **Select** **OpenCode Go** or **OpenCode Zen**.
7. **Press Enter** to accept the default group name.
8. **Paste your API key** when prompted (stored by VS Code in your language-models configuration).
9. **Pick the models** you want enabled.
10. **Select any OpenCode model** from the picker and start chatting. 🚀

> **💡 Tips:**
>
> - Go and Zen are **separate provider groups**: both can be active simultaneously. Switch anytime from the picker.
> - If a model shows in **Language Models** view but not the chat picker, hover its row and click the **eye icon (👁)** to enable it.
> - Set `opencodego.freeOnly: false` to reveal **paid Zen models** in the picker.

</details>

---

## 🎬 Demo

<p align="center">
  <img src="docs/screenshots/model-picker.gif" alt="Copilot Chat model picker showing OpenCode models" width="480" />
</p>

_Selecting an OpenCode model from the Copilot Chat model picker._

---

## 🧠 Models

The extension fetches **live model lists** on every startup from:

| Provider         | Endpoint                               | Cost                                                                         |
| ---------------- | -------------------------------------- | ---------------------------------------------------------------------------- |
| **OpenCode Go**  | `https://opencode.ai/zen/go/v1/models` | $10/mo ($5 first month promo); usage limits: 5h/$12, weekly/$30, monthly/$60 |
| **OpenCode Zen** | `https://opencode.ai/zen/v1/models`    | rotating free models + pay-as-you-go for premium models                      |

### ⭐ OpenCode Go ($10/mo subscription, $5 first month promo)

Curated open coding models, refreshed live from the endpoint. Deprecated/legacy models (e.g. `glm-5`, `kimi-k2.5`, `minimax-m2.5`, `mimo-v2-pro`, `mimo-v2-omni`, `qwen3.5-plus`) are filtered before registration.

| Model                                   |       Context | Max Output | Highlights               | Included usage/mo |
| --------------------------------------- | ------------: | ---------: | ------------------------ | ----------------- |
| `deepseek-v4-pro` / `deepseek-v4-flash` | **1,000,000** |    384,000 | 🧠 Reasoning `off`→`max` | $15 / $30         |
| `gpt-5.6-luna`                          | **1,050,000** |    128,000 | 🛣️ `/responses` API      | $15               |
| `grok-4.6`                              |       500,000 |    500,000 | 🧠 + 🖼️ Vision           | $15               |
| `glm-5.3`                               | **1,000,000** |    131,072 | 🧠 Always-on thinking    | $15               |
| `glm-5.3-flash`                         | **1,000,000** |    131,072 | 🧠 + 🖼️ Vision           | $15               |
| `glm-5.2`                               | **1,000,000** |    131,072 | 🧠 `off`/`high`/`max`    | $60               |
| `glm-5.1`                               |       202,752 |     32,768 | 🧠 `off`/`high`/`max`    | $60               |
| `kimi-k3`                               | **1,048,576** |    131,072 | 🧠 + 🖼️ Vision           | $15               |
| `kimi-k2.7-code`                        |       262,144 |    262,144 | 🧠 Always-on thinking    | $60               |
| `kimi-k2.6`                             |       262,144 |     65,536 | 🧠 + 🖼️ Vision           | $60               |
| `mimo-v2.5-pro` / `mimo-v2.5`           | **1,048,576** |    128,000 | 🧠 Effort `low`→`high`   | $15 / $60         |
| `minimax-m3`                            | **1,000,000** |    131,072 | 🧠 + 🖼️ Vision           | $60               |
| `minimax-m2.7`                          |       204,800 |    131,072 | 🧠 `on`/`off`            | $60               |
| `qwen3.8-max` / `qwen3.8-flash`         | **1,000,000** |    131,072 | 🧠 `thinking_budget`     | $15 / $30         |
| `qwen3.7-max`                           | **1,000,000** |     65,536 | 🧠 `thinking_budget`     | $30               |
| `qwen3.7-plus` / `qwen3.6-plus`         | **1,000,000** |     65,536 | 🧠 + 🖼️ Vision           | $60               |
| `omen-alpha`                            |       500,000 |    128,000 | 🧠 + 🖼️ Vision           | **$100**          |
| `hy4-preview`                           | **1,024,000** |     64,000 | 🧠 Preview               | $30               |
| `hy3`                                   |       256,000 |    128,000 | 🧠 Text-only             | $60               |

> **Usage:** most Go models include **$60/mo** of included usage; premium models include less (`glm-5.3`, `glm-5.3-flash`, `gpt-5.6-luna`, `grok-4.6`, `kimi-k3`, `qwen3.8-max`, `deepseek-v4-pro`, `deepseek-v4-flash-vision-exp`, `mimo-v2.5-pro` at $15/mo; `qwen3.8-flash`, `qwen3.7-max`, `deepseek-v4-flash`, `hy4-preview` at $30/mo), and `omen-alpha` includes a larger **$100/mo**. Cheaper per-token models stretch their allowance further, so request counts vary widely: the docs estimate ~226K requests/mo on Muse Spark 1.3 vs ~490 on Kimi K3. If you hit a limit, keep using the free Zen models (or enable the "Use balance" option in the Zen console).

### 🆓 OpenCode Zen free models (no payment needed)

OpenCode Zen offers **rotating free models**, no balance required. Currently free: **Big Pickle** (stealth model), DeepSeek V4 Flash Free, MiMo-V2.5 Free, Hy3 Free, Laguna S 2.1 Free, Ling-3.0-tiny Free, Nemotron 3 Ultra Free, and Nemotron 3.5 Lightning Free. Without a balance, rate limits are low. Adding $20+ to your Zen balance significantly improves rate limits on free models.

> **Note:** Per the OpenCode docs, free models are all offered **for a limited time** and rotate periodically. The table shows current offerings; availability may change.

| Model                         |   Context | Max Output | Vendor     |
| ----------------------------- | --------: | ---------: | ---------- |
| `big-pickle`                  |   200,000 |     32,000 | 🥒 Stealth |
| `deepseek-v4-flash-free`      |   200,000 |    128,000 | DeepSeek   |
| `mimo-v2.5-free`              |   200,000 |     32,000 | Xiaomi     |
| `hy3-free`                    |   190,000 |     64,000 | OpenCode   |
| `laguna-s-2.1-free`           |   256,000 |     32,000 | OpenCode   |
| `ling-3.0-tiny-free`          |   262,144 |     32,768 | OpenCode   |
| `nemotron-3-ultra-free`       | 1,000,000 |    128,000 | NVIDIA     |
| `nemotron-3.5-lightning-free` |   262,144 |    262,144 | NVIDIA     |

### 💰 OpenCode Zen paid models (requires balance)

Add a payment method to your Zen account to unlock these models at pay-as-you-go rates. OpenCode passes provider price drops through at cost. Prices per 1M tokens.

| Model                                                                                                   |       Context | Max Output | Input / Output per 1M tokens |
| ------------------------------------------------------------------------------------------------------- | ------------: | ---------: | ---------------------------- |
| `claude-fable-5`                                                                                        | **1,000,000** |    128,000 | $10 / $50                    |
| `claude-opus-5` / `claude-opus-4-8` / `claude-opus-4-7` / `claude-opus-4-6`                             | **1,000,000** |    128,000 | $5 / $25                     |
| `claude-sonnet-5`                                                                                       | **1,000,000** |    128,000 | $2 / $10                     |
| `claude-sonnet-4-6` / `claude-sonnet-4-5`                                                               | **1,000,000** |     64,000 | $3 / $15                     |
| `claude-haiku-4-5`                                                                                      |       200,000 |     64,000 | $1 / $5                      |
| `gpt-5.6-sol` / `gpt-5.6-terra` / `gpt-5.6-luna`                                                        | **1,050,000** |    128,000 | $0.20–$5 / $1.20–$30         |
| `gpt-5.5` / `gpt-5.4`                                                                                   | **1,050,000** |    128,000 | $2.50–$5 / $15–$30           |
| `gpt-5.5-pro` / `gpt-5.4-pro`                                                                           | **1,050,000** |    128,000 | $30 / $180                   |
| `gpt-5.4-mini` / `gpt-5.4-nano` / `gpt-5.3-codex` / `gpt-5.2` / `gpt-5.1` / `gpt-5` / `gpt-5-nano`      |       400,000 |    128,000 | $0.05–$1.75 / $0.40–$14      |
| `gemini-3.6-flash` / `gemini-3.5-flash` / `gemini-3.5-flash-lite` / `gemini-3.1-pro` / `gemini-3-flash` | **1,048,576** |     65,536 | $0.30–$2 / $2.50–$12         |
| `grok-4.6`                                                                                              |       500,000 |    500,000 | $2 / $6                      |
| `grok-build-0.1`                                                                                        |       256,000 |    256,000 | $1 / $2                      |
| `deepseek-v4-pro` / `deepseek-v4-flash`                                                                 | **1,000,000** |    384,000 | $0.14–$1.74 / $0.28–$3.84    |
| `qwen3.6-plus` / `qwen3.5-plus`                                                                         |       262,144 |     65,536 | $0.20–$0.50 / $1.20–$3.00    |
| `kimi-k3`                                                                                               | **1,048,576** |    131,072 | $3 / $15                     |
| `kimi-k2.7-code`                                                                                        |       262,144 |    262,144 | $0.95 / $4                   |
| `kimi-k2.6`                                                                                             |       262,144 |     65,536 | $0.95 / $4                   |
| `glm-5.3` / `glm-5.3-flash`                                                                             | **1,000,000** |    131,072 | $0.15–$1.40 / $0.50–$4.40    |
| `muse-spark-1.3` / `muse-spark-1.2`                                                                     | **1,048,576** |    131,072 | $1.25 / $4.25                |
| `glm-5.2`                                                                                               | **1,000,000** |    131,072 | $1.40 / $4.40                |
| `glm-5.1`                                                                                               |       204,800 |    131,072 | $1.40 / $4.40                |
| `minimax-m3`                                                                                            |       512,000 |    128,000 | $0.30 / $1.20                |
| `minimax-m2.7`                                                                                          |       204,800 |    131,072 | $0.30 / $1.20                |

> Set `opencodego.freeOnly: false` to show paid Zen models in the picker (default shows only free models).

<details>
<summary><b>🔬 How model metadata is resolved (3-tier fallback)</b></summary>

Limits and capabilities resolve in this priority order:

1. **Live metadata** from OpenCode `/models` endpoint
2. **6-hour models.dev snapshot** cached in VS Code `globalState`
3. **Bundled fallback catalog** shipped with the extension (works offline)

Deprecated/unavailable models are filtered before registration. Per-provider limits tracked separately (Go vs Zen) so shared models (e.g. `glm-5.1`, `qwen3.6-plus`) use correct values for each.

</details>

<details>
<summary><b>🛣️ Endpoint routing per model family</b></summary>

| Family                                                | Endpoint                         | Why                  |
| ----------------------------------------------------- | -------------------------------- | -------------------- |
| Zen GPT (`gpt-*`)                                     | `/responses`                     | OpenAI native        |
| Zen Gemini (`gemini-*`)                               | `:streamGenerateContent?alt=sse` | Google native        |
| Zen Claude (`claude-*`) + Go MiniMax (`minimax-m2.*`) | `/messages`                      | Anthropic-compatible |
| Everything else (Qwen, DeepSeek, GLM, Kimi, MiMo…)    | `/chat/comple