# 1. Executive Summary
## Core Concept & Value
**InflameCop** is a multi-agent system that autonomously audits cellular inflammation risks from food photography by combining multi-modal perception with context-aware functional medicine reasoning.

| Section | Description |
| :--- | :--- |
| **Market Opportunity** | **$4.3T global wellness market.** 68% of urban professionals suffer from fatigue or brain fog, which is clinically rooted in **Neuroinflammation** and **Mitochondrial Dysfunction**. Yet 100% of mass-market nutrition apps miss these cellular inflammation triggers. |
| **Solution Type** | Privacy-first personal health concierge powered by a specialized **3-agent system (Security Guard, Context Router, Medical Analyzer)**. |
| **Key Innovation** | Context-aware molecular logic that dynamically infers hidden restaurant cooking patterns combined with zero-friction image-payload guardrails. |
| **Time to Value** | Reduces 10-minute stressful manual meal-logging or blind guesswork to a **< 5-second personalized biological verdict**. |
| **Cost Efficiency** | $0 user maintenance or app subscription fees, costing only **~$0.005 token overhead** per dish analysis using `gemini-2.5-flash`. |

---

# 2. Problem Statement: The Hidden Cellular Fire

> **Urban professionals aren't just tired—their cells are on fire.** Modern meals are packed with hidden, highly inflammatory restaurant oils and toxic AGE surges, yet 100% of legacy trackers are completely blind to these molecular triggers, forcing users to count calories while leaving their cellular health unprotected.

* **The Silent Epidemic**: Chronic inflammation drives **50% of global deaths**, causing **68% of urban professionals** to suffer from daily fatigue and "brain fog."
* **The Dietary Triggers**: **70%–80%** of these conditions are diet-driven. Modern restaurant dining exposes consumers to a toxic **20:1 Omega-6 ratio** (via cheap seed oils) and a **2,200% surge in Advanced Glycation End-products (AGEs)** from high-temperature frying, which actively shuts down cellular energy (mitochondria).
* **The Legacy Blindspot**: In a $4.3T wellness market, 100% of mass-market nutrition apps are completely blind to these molecular triggers. They force users into tedious calorie-counting while letting hidden inflammatory damage slip through.
---
# 3. Solutions & Why Agents
## Solutions
## Why Agents?
## Key Features

---
# 4. Architecture

## Diagram 1 - 4 layers structure diagram
```mermaid
graph TD
    %% 樣式定義
    classDef orchestrate fill:#2a1b40,stroke:#a855f7,stroke-width:2px,color:#fff,rx:10px;
    classDef specialized fill:#1f1c18,stroke:#f59e0b,stroke-width:2px,color:#fff,rx:8px;
    classDef specializedSec fill:#1e2019,stroke:#eab308,stroke-width:2px,color:#fff,rx:8px;
    classDef specializedRag fill:#152219,stroke:#22c55e,stroke-width:2px,color:#fff,rx:8px;
    classDef synthesis fill:#0f1d24,stroke:#06b6d4,stroke-width:2px,color:#fff,rx:10px;
    classDef data fill:#18181b,stroke:#3f3f46,stroke-width:1.5px,color:#d4d4d4;
    classDef protocol stroke:#f97316,stroke-width:1.5px,stroke-dasharray: 5 5,color:#f97316;

    %% Orchestration Layer
    subgraph Orchestration_Layer [Orchestration Layer 編排調度層]
        CR[CONTEXT ROUTER AGENT <br/> <i>InflameCop Coordinator</i>]:::orchestrate
    end

    %% Specialized Agent Layer
    subgraph Specialized_Agent_Layer [Specialized Agent Layer 專用智能體層]
        SG[SECURITY GUARD AGENT <br/> <small>Security/Input Validation</small>]:::specializedSec
        VP[VISION PERCEPTION AGENT <br/> <small>Computer Vision</small>]:::specialized
        CP[CONTEXT PENALTY AGENT <br/> <small>Context Logic</small>]:::specialized
        KR[KNOWLEDGE RETRIEVAL AGENT <br/> <small>RAG</small>]:::specializedRag
    end

    %% Synthesis Layer
    subgraph Synthesis_Layer [Synthesis Layer 綜合分析層]
        BA[BIOMARKER ANALYZER AGENT]:::synthesis
    end

    %% Data & Knowledge Integration Layer
    subgraph Data_Layer [Data & Knowledge Integration Layer 數據與知識整合層]
        DB1[(WHO Chronic<br/>Disease Index)]:::data
        DB2[(Mount Sinai<br/>AGE DB)]:::data
        DB3[(Google GenAI<br/>SDK)]:::data
    end

    %% 連線與協定 (Agent Protocol)
    CR --> SG
    CR --> VP
    CR --> CP
    CR --> KR

    SG --> BA
    VP --> BA
    CP --> BA
    KR --> BA

    KR --> DB1
    KR --> DB2
    BA --> DB3
```
### Agent Specifications


## Diagram 2 - MCP
```mermaid
graph TD
    %% Styling
    classDef orchestrator fill:#4c1d95,stroke:#a78bfa,stroke-width:2px,color:#fff;
    classDef skill fill:#1e293b,stroke:#f59e0b,stroke-width:1.5px,color:#f8fafc;
    classDef db fill:#0f172a,stroke:#3b82f6,stroke-width:1.5px,color:#38bdf8;
    classDef model fill:#064e3b,stroke:#34d399,stroke-width:2px,color:#fff;

    %% Orchestrator
    subgraph Orchestration_Layer [Orchestration Layer 核心編排層]
        CR[Context Router / Coordinator <br/> <b>Unified Entrypoint: /api/analyze</b>]:::orchestrator
    end

    %% Dynamic Skills
    subgraph Specialist_Skills [Specialist Skills 動態載入技能庫]
        SG[Skill 1: Security Guard <br/> Input & Format Shield]:::skill
        VP[Skill 2: Vision Perception <br/> Image Feature Extraction]:::skill
        CP[Skill 3: Context Penalty <br/> Chrono & Oil Graded Penalty]:::skill
        KR[Skill 4: Knowledge Retrieval <br/> RAG & Database Mapping]:::skill
        BA[Skill 5: Biomarker Synthesis <br/> Clinical Logic & Body State]:::skill
    end

    %% Model Pool
    subgraph Model_Runtime [Google GenAI LLM Runtime Engine]
        GM35[Gemini 3.5 Flash <br/> <b>Primary sweet spot</b>]:::model
        GFL[Gemini Flash Latest <br/> <i>Fallback 1</i>]:::model
        GM31[Gemini 3.1 Flash-Lite <br/> <i>Fallback 2</i>]:::model
        G25F[Gemini 2.5 Flash <br/> <i>Fallback 3</i>]:::model
        G25P[Gemini 2.5 Pro <br/> <i>Deep Reasoning Fallback</i>]:::model
    end

    %% Databases
    subgraph Data_Integration [Data & Knowledge Integration Layer]
        MS[Mount Sinai AGE DB <br/> <i>Advanced Glycation End-products</i>]:::db
        WHO[WHO Chronic Disease Index <br/> <i>Systemic Inflammation Factors</i>]:::db
        UDB[User History Log DB <br/> <i>Temporal Trajectory</i>]:::db
    end

    %% Connections
    User([User Food Photo & Biometrics]) -->|HTTP POST| CR
    CR -->|1. Dynamically Load| SG
    CR -->|2. Dynamically Load| VP
    CR -->|3. Dynamically Load| CP
    CR -->|4. Dynamically Load| KR
    CR -->|5. Dynamically Load| BA
    
    %% Skills requesting database / facts
    KR -.->|Query| MS
    KR -.->|Query| WHO
    BA -.->|Query| UDB

    %% Synthesis to LLM
    SG & VP & CP & KR & BA -->|Single Consolidated Prompt Context| GM35
    GM35 -.->|Failover| GFL -.->|Failover| GM31 -.->|Failover| G25F -.->|Failover| G25P
    
    %% Return
    GM35 -->|Deterministic JSON Output| CR
    CR -->|Synthesized Interactive UI| User
```
---
# 4. The Build 
## 🛠️ Tech Stack
## Installation
## Usage
## Development Process

---
# n. Kaggle 5 Days Topics Coverage

---
# n. Next Steps

---
# n. Citation

---
# n. Q & A

