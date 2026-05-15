# 🧪 lab-ai-agents

> A plug-in framework for deploying AI agent workforces in scientific and lab environments.

![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=flat-square&logo=node.js&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)
![C#](https://img.shields.io/badge/C%23-.NET-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![Claude AI](https://img.shields.io/badge/Claude-Anthropic-D97757?style=flat-square)
![GMP](https://img.shields.io/badge/GMP-Ready-2ea44f?style=flat-square)
![21 CFR Part 11](https://img.shields.io/badge/21_CFR_Part_11-Compliant-red?style=flat-square)
![GAMP 5](https://img.shields.io/badge/GAMP_5-Aware-blueviolet?style=flat-square)

Most AI toolkits are built for general software teams. This one is built for labs — where compliance isn't optional, instrumentation matters, and the people reviewing your outputs need audit trails, not just answers.

**lab-ai-agents** is a modular, plug-in framework that lets teams deploy AI agents — virtual reviewers, technical writers, utility processors, and workflow processors — as a configurable workspace. Built on Node.js APIs with Python processing hooks, it is responsive, professionally themed, and designed so users can select exactly the agents and capabilities they need.

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 🔌 **Plug-in Architecture** | Select only the agents and modules your workspace needs. Drop in new capabilities without touching the core framework. |
| 🤖 **Virtual Agent Workforce** | Deploy specialized AI agents — reviewers, technical writers, code reviewers — each with defined roles and review gates. |
| 🐍 **Python Processing Hooks** | Node.js handles the API layer; Python scripts handle data processing, ML inference, and scientific workflows behind each request. |
| 📡 **REST API First** | Every agent and workflow is exposed as a REST endpoint — plug into existing LIMS, instrumentation software, or custom pipelines. |
| 🎨 **Responsive & Themed UI** | Professionally styled, responsive interface. Dark/light mode, configurable workspace layout, built for real lab environments. |

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────┐
│              lab-ai-agents Framework             │
├──────────────┬──────────────┬───────────────────┤
│  Frontend UI │  Node.js API │  Python Workers   │
│  Responsive  │  REST Layer  │  Data Processing  │
│  Themed      │  Auth/Audit  │  ML Inference     │
│  Plug-in WS  │  Routing     │  Workflow Scripts │
├──────────────┴──────────────┴───────────────────┤
│              Agent Orchestration Layer           │
│ Virtual · Tech Writer · Validator · Coordinator  │
├─────────────────────────────────────────────────┤
│           Claude AI (via Anthropic API)          │
│        Sonnet · Tool Use · Agent Loops           │
└─────────────────────────────────────────────────┘
```

### Request Flow

```
User / LIMS / Instrument
        │
        ▼
  Node.js REST API  ──── Auth + Audit Trail
        │
        ▼
  Agent Orchestrator  ──── Selects agent(s) based on request type
        │
   ┌────┴────┐
   ▼         ▼
Claude AI   Python Script
(reasoning) (data processing / ML)
        │
        ▼
  Review Gate  ──── Virtual QA / Approver agent
        │
        ▼
  Response + Audit Record
```

---

## 🔌 Available Plug-ins

| Plug-in | Description |
|---|---|
| 📋 **Review Agent** | Virtual reviewer versed in specific domains |
| ✍️ **Tech Writer Agent** | Generates and validates code documentation |
| 🔬 **Data Processor** | Python hooks for instrument data and assay results |
| 🧠 **ML Inference** | ML.Net / ONNX / Python model integration |
| 📊 **Report Builder** | Automated report generation with audit metadata |
| 🔗 **LIMS Connector** | REST hooks for existing LIMS and lab systems |

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- Python 3.10+
- Anthropic API key

### Install & Run

```bash
# Clone the repo
git clone https://github.com/scott-castetter/lab-ai-agents.git
cd lab-ai-agents

# Install Node dependencies
npm install

# Install Python dependencies
pip install -r requirements.txt

# Configure environment
cp .env.example .env
# Add your ANTHROPIC_API_KEY and settings

# Start the API server
npm start
```

### Configure Your Workspace

```json
{
  "agents": ["reviewer", "tech-writer", "data-processor"],
  "theme": "dark",
  "compliance": {
    "cfr_part_11": true,
    "gamp5": true,
    "audit_trail": true
  },
  "python_hooks": {
    "enabled": true,
    "scripts_dir": "./python/workflows"
  }
}
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| API Server | Node.js · Express |
| AI Agents | Claude (Anthropic API) · Tool Use |
| Data Processing | Python 3 · Pandas · NumPy |
| ML Inference | ML.Net · ONNX · scikit-learn |
| Frontend | Responsive UI · Dark/Light theme |
| Database | SQL Server · SQLite |
| Auth & Audit | JWT · Immutable audit logs |

---

## 📁 Project Structure

```
lab-ai-agents/
├── api/                  # Node.js Express API layer
│   ├── routes/           # REST endpoint definitions
│   ├── middleware/        # Auth, audit, validation
│   └── agents/           # Agent orchestration logic
├── python/               # Python processing workers
│   ├── workflows/        # Workflow scripts
│   ├── ml/               # ML inference hooks
│   └── processors/       # Data processing modules
├── plugins/              # Drop-in agent plug-ins
│   ├── reviewer/
│   ├── tech-writer/
│   ├── data-processor/
│   └── lims-connector/
├── ui/                   # Responsive themed frontend
├── config/               # Workspace configuration
└── docs/                 # Documentation & validation records
```

---

## 🗺️ Roadmap

- [ ] Additional instrument connectors (Waters, Agilent, Tecan)
- [ ] LIMS-specific plug-ins (Titian Mosaic, LabVantage)
- [ ] Expanded ML.Net / ONNX model registry
- [ ] Multi-site deployment support
- [ ] Enhanced validation documentation generator

---

## 👤 About the Author

Built by **Scott Castetter** — scientist and software developer with 30 years bridging the gap between the bench and the software that runs it. Custom LIMS systems, lab automation platforms, ML pipelines, and AI agent workflows.

[LinkedIn](https://www.linkedin.com/in/scastetter/) · [GitHub](https://github.com/scott-castetter)

---

*Built at the intersection of laboratory science and software — for the people who live in both worlds.*
