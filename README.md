<div align="center">

# 🛍️ GenPark Next-Gen Features Suite (2026)

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-Compatible-blue.svg)](https://openclaw.ai)
[![GenPark](https://img.shields.io/badge/Platform-GenPark.ai-orange.svg)](https://genpark.ai)
[![Node.js CI](https://img.shields.io/badge/Node.js-%3E%3D20.0.0-brightgreen.svg)](https://nodejs.org)
[![MCP](https://img.shields.io/badge/Protocol-MCP%20Enabled-purple.svg)](https://modelcontextprotocol.io)

**Cutting-Edge Autonomous AI Commerce & Discovery Infrastructure for [GenPark](https://genpark.ai)**

</div>

---

## 🌟 Executive Overview

As autonomous AI agents evolve from conversational advisors into active shopping proxies (inspired by recent 2026 milestones in Meta Muse and Stripe Link Agent Wallet), platforms like **[GenPark.ai](https://genpark.ai)** require rock-solid safeguards, mathematical cart optimization, anti-spoof review intelligence, and community-driven trend discovery.

This repository implements **4 flagship features** designed to scale GenPark's agentic commerce ecosystem:

| Feature | Name | Purpose | Value Proposition |
|---|---|---|---|
| 🛡️ | **Agent Wallet Guard** | Safe Autonomous Spending & Checkout | Enforces per-order caps, rolling daily allowance, HMAC-SHA256 human escalations, and tamper-evident virtual receipts. |
| 🛒 | **Cross-Store Basket Optimizer** | Multi-Merchant Smart Cart Solver | Combinatorial knapsack solver factoring in item prices, shipping fee tiers, and free shipping thresholds across sellers. |
| 🔍 | **Product TruthGuard** | Anti-Hallucination Review Forensics | Exposes AI-generated astroturfing reviews, calculates rating incongruence, and extracts real-world product flaw clusters. |
| 📡 | **Circle Trend Radar** | Community Insight (洞见) Synthesizer | Monitors viral product velocity across GenPark Circle discussions and auto-drafts editorial-ready insight publications. |

---

## 🚀 Quick Start

### Installation

```bash
git clone https://github.com/alphaparkinc/genpark-next-features.git
cd genpark-next-features
npm install
```

### Run Tests

Zero external dependencies required (uses Node.js native test runner):

```bash
npm test
```

### Interactive CLI

```bash
# Test Agent Wallet Guard (auto-approval vs human escalation)
node bin/genpark-cli.js wallet 45 GenPark-Direct
node bin/genpark-cli.js wallet 250 GenPark-Direct

# Test Cross-Store Basket Optimizer
node bin/genpark-cli.js basket mechanical-keyboard,desk-mat,usb-c-hub

# Test Product TruthGuard Review Audit
node bin/genpark-cli.js audit

# Test Circle Trend Radar & Article Synthesizer
node bin/genpark-cli.js radar
```

---

## 📦 Feature Deep-Dive

### 1. 🛡️ Agent Wallet Guard (`src/wallet-guard/`)

Autonomous shopping agents cannot be given unrestricted credit cards. `AgentWalletGuard` implements:
- **Budget Policy**:
  - `maxPerOrder` ($150 default): Purchases exceeding this threshold trigger a cryptographic confirmation challenge.
  - `dailyAllowance` ($500 default): Rolling 24-hour spend cap.
  - `minMerchantTrustScore` (0.75 default): Low-reputation merchants automatically require human approval.
  - Prohibited categories: Blocks automated agent purchases of restricted goods.
- **HMAC-SHA256 Challenge Flow**:
  - Generates timed challenge tokens with a 15-minute TTL.
  - Validates approval signatures before releasing funds.
- **Virtual Receipt Ledger**:
  - Generates a SHA-256 tamper-evident digital receipt verifiable via GenPark protocol.

### 2. 🛒 Cross-Store Basket Optimizer (`src/basket-optimizer/`)

When a user or agent builds a multi-item wishlist, buying everything from a single seller is rarely the cheapest option, but splitting across too many sellers incurs high shipping fees.

The solver computes:
- $\min \left( \sum \text{Price}_i + \sum \text{Shipping}(\text{Merchant}_j) \right)$
- Applies free-shipping qualification triggers (e.g. Free shipping when cart $\ge \$50$).
- Outputs 3 distinct strategies:
  1. **Cheapest Net Cost Plan**
  2. **Single-Store Consolidated Plan** (minimal package count)
  3. **Fastest Delivery Plan**

### 3. 🔍 Product TruthGuard (`src/truth-guard/`)

E-commerce is plagued by incentivized reviews and generic LLM-generated boilerplates. `ProductTruthGuard`:
- Calculates **Type-Token Ratio (TTR)** and lexical burstiness.
- Flags cliché bot phrases (`"game-changer"`, `"exceeded all my expectations"`, `"in conclusion..."`).
- Identifies **Rating Incongruence** (5-star ratings with severe defect complaints).
- Isolates verified negative feedback into structured flaw categories:
  - Durability & Build Quality
  - Sizing & Ergonomics
  - Battery & Electronics
  - Customer Service & Shipping
- Produces an adjusted **Authentic Rating** and **Trust Grade (A, B, C, D, F)**.

### 4. 📡 Circle Trend Radar (`src/circle-radar/`)

GenPark's social community Circle is where shoppers share insights. `CircleTrendRadar`:
- Ingests discussion streams, calculating engagement velocity and acceleration.
- Ranks emerging items (`STEADY`, `RISING`, `VIRAL`).
- Automatically synthesizes editorial-grade **Circle Insights (洞见)** in Markdown with community quotes and direct purchase links.

---

## 🤖 MCP (Model Context Protocol) Integration

This package includes a production-ready stdio MCP server for OpenClaw, Claude Desktop, and Antigravity:

```bash
node mcp/server.js
```

### Available MCP Tools:
- `genpark_wallet_checkout`: Safely evaluate and execute orders with budget guard.
- `genpark_optimize_basket`: Solve multi-item cart allocation.
- `genpark_audit_reviews`: Audit reviews and extract real flaws.
- `genpark_circle_trend_radar`: Analyze discussions and draft Circle insights.

---

## 📄 License

MIT © 2026 GenPark (AlphaPark Inc). Built for the GenPark and OpenClaw agent ecosystem.
