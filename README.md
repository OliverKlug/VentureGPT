# VC Investment Committee Simulator

[![n8n](https://img.shields.io/badge/n8n-Workflow-FF6D5A?logo=n8n)](https://n8n.io) [![Telegram](https://img.shields.io/badge/Telegram-Bot-26A5E4?logo=telegram)](https://telegram.org) [![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-412991?logo=openai)](https://openai.com)

> AI-powered venture capital investment committee that evaluates startup pitches through multiple specialized analyst perspectives.

## 🎯 Overview

A multi-agent AI system that simulates a professional VC investment committee. Submit startup ideas via Telegram (text or voice), and receive comprehensive analysis from 5 specialized AI analysts plus a synthesized investment recommendation.

**Why this exists:** To understand how VCs think, automate complex decision-making frameworks, and practice structured investment analysis.

## ✨ Features

### Multi-Agent Analysis System

* **5 Specialized AI Analysts:**

  * 📊 **Market Sizing Analyst** - TAM/SAM/SOM analysis, growth potential

  * 👥 **Founder Fit Analyst** - Team evaluation, domain expertise

  * 🎯 **Product-Market Fit Analyst** - Problem validation, solution fit

  * 🏰 **Competitive Moat Analyst** - Porter's Five Forces, defensibility

  * 💰 **Valuation Analyst** - Unit economics, LTV:CAC, burn rate

### VC Framework Application

* Porter's Five Forces

* TAM/SAM/SOM methodology

* Unit economics analysis

* LTV:CAC ratios

* Competitive landscape mapping

### User Experience

* 🎤 Voice-to-text pitch transcription

* 📱 Telegram bot interface

* ⚡ Parallel agent execution

* 📊 Structured scoring (1-10 scale)

* 🎯 Final investment decision with rationale

## 🏗️ Architecture

```
graph TD
    A[User Pitch via Telegram] --> B[Voice-to-Text Conversion]
    B --> C[Pitch Analysis Dispatcher]
    C --> D1[Market Sizing Agent]
    C --> D2[Founder Fit Agent]
    C --> D3[PMF Agent]
    C --> D4[Moat Agent]
    C --> D5[Valuation Agent]
    D1 --> E[Synthesis Agent]
    D2 --> E
    D3 --> E
    D4 --> E
    D5 --> E
    E --> F[Investment Decision]
    F --> G[Telegram Response]
```

## 🚀 Quick Start

### Prerequisites

* **n8n** instance (local or cloud)

* **OpenAI API** key (GPT-4 recommended)

* **Telegram Bot** token

### Installation

1. **Clone the repository**

```
git clone https://github.com/yourusername/vc-committee-simulator.git
cd vc-committee-simulator
```

1. **Import n8n workflow**

   * Open n8n

   * Go to Workflows → Import

   * Select `vc-committee-workflow.json`

2. **Configure credentials**

   * Add Telegram Bot token

   * Add OpenAI API key

   * Set up webhook (if using cloud n8n)

3. **Activate workflow**

   * Click "Activate" in n8n

## 💬 Usage

### Telegram Commands

```
/start - Initialize the VC simulator
/pitch - Submit a startup idea for analysis
/help - Show available commands
/examples - See sample pitches
```

### Pitch Submission

**Text Input:**

```
/pitch A marketplace connecting freelance designers with small businesses. 
Monthly subscription model at $99/mo. Targeting 500k small businesses in DACH region.
```

**Voice Input:** Record a voice message describing your startup idea - it will be automatically transcribed.

## 📊 Analysis Output

Each pitch receives:

### Individual Analyst Scores (1-10)

* Market Sizing: Score + reasoning

* Founder Fit: Score + reasoning

* Product-Market Fit: Score + reasoning

* Competitive Moat: Score + reasoning

* Valuation: Score + reasoning

### Final Investment Decision

* **Overall Score** (weighted average)

* **Recommendation:** Pass / Maybe / Invest

* **Key Strengths** (top 3)

* **Red Flags** (if any)

* **Next Steps** (suggested actions)

## 🔧 Configuration

### OpenAI Model Settings

Default: `gpt-4-turbo-preview`

Alternative models:

* `gpt-4` - More accurate, slower

* `gpt-3.5-turbo` - Faster, less accurate

### Agent Prompts

Each agent has a specialized system prompt defining:

* Role and expertise

* Evaluation frameworks

* Output format (JSON structured)

* Scoring criteria

**Location:** n8n workflow → AI Agent nodes → System Prompts

### Synthesis Logic

**Weighted Scoring:**

* Market Sizing: 25%

* Founder Fit: 20%

* Product-Market Fit: 25%

* Competitive Moat: 15%

* Valuation: 15%

**Decision Thresholds:**

* 8.0+ → **Invest** (strong recommendation)

* 6.0-7.9 → **Maybe** (needs due diligence)

* <6.0 → **Pass** (not suitable)

## 🧪 Example Pitches

### SaaS B2B

```
AI-powered sales forecasting tool for mid-market companies. 
$199/user/month. 50M TAM in US. Founded by ex-Salesforce VP.
```

### Consumer App

```
Fitness app using AR to gamify home workouts. 
Freemium model, $9.99/mo premium. 20M potential users globally.
```

### Marketplace

```
P2P marketplace for renting camera equipment. 
10% transaction fee. $2B camera rental market in Europe.
```

## 🛠️ Tech Stack

ComponentTechnology**Workflow Automation**n8n**AI Models**OpenAI GPT-4**Bot Interface**Telegram Bot API**Voice Processing**OpenAI Whisper (via Telegram)**Architecture**Multi-Agent System

## 📁 Project Structure

```
vc-committee-simulator/
├── vc-committee-workflow.json    # Main n8n workflow
├── README.md                      # This file
├── docs/
│   ├── agent-prompts.md          # All agent system prompts
│   ├── frameworks.md             # VC frameworks explained
│   └── examples.md               # Sample analyses
└── LICENSE
```

## 🎓 What I Learned

### AI Multi-Agent Systems

* Defining clear agent personas and responsibilities

* Parallel execution vs. sequential processing

* Synthesis logic for aggregating diverse opinions

### VC Frameworks

* How professional investors evaluate opportunities

* Importance of market sizing (TAM/SAM/SOM)

* Unit economics as key valuation driver

* Competitive moat = long-term defensibility

### Technical Challenges

* Structuring AI outputs for reliable parsing

* Voice transcription accuracy trade-offs

* Balancing agent autonomy with consistent scoring

## 🐛 Known Limitations

* **Voice quality:** Background noise affects transcription

* **Hallucinations:** AI may invent market data

* **Bias:** Inherits OpenAI model biases

* **No memory:** Each pitch is evaluated independently

* **Cost:** GPT-4 API calls can add up (5 agents per pitch)

## 🚀 Future Enhancements

* Add historical pitch database

* Include industry-specific benchmarks

* Multi-round evaluation (seed vs. Series A)

* Comparison mode (2 pitches side-by-side)

* Export to PDF report

* Integration with pitch deck uploads

* Real-time market data enrichment

## 📝 Contributing

Contributions welcome! Areas for improvement:

* Additional analyst perspectives (ESG, Tech Due Diligence)

* Alternative VC frameworks

* Better synthesis algorithms

* UI improvements

## 🙏 Acknowledgments

* Inspired by real VC investment committee processes

* Frameworks based on industry best practices

* Built with n8n's powerful workflow automation

---

<p align="center"> <sub>Built with n8n + OpenAI | README created with AI assistance</sub> </p>
