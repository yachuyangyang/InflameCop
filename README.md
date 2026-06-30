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
## Agents/Skills Architecture

```mermaid
flowchart TD
    %% Global Light-Themed Styling Config
    classDef coordinator fill:#f3e8ff,stroke:#7c3aed,stroke-width:2px,color:#4c1d95,font-weight:bold;
    classDef fallbackBox fill:#eff6ff,stroke:#3b82f6,stroke-width:1px,stroke-dasharray: 4 4,color:#1e40af,font-size:11px;
    classDef skillGroup fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px,color:#1e293b,font-weight:bold;
    classDef skill fill:#ffffff,stroke:#64748b,stroke-width:1px,color:#334155,font-size:11px;
    classDef db fill:#f0fdf4,stroke:#16a34a,stroke-width:1.5px,color:#14532d;
    classDef output fill:#fef3c7,stroke:#d97706,stroke-width:2px,color:#92400e,font-weight:bold;

    %% --- USER INPUT TRIGGER ---
    Input([👤 User Uploads Meal Image + User Tags]) --> Coordinator

    %% ==========================================
    %% 1. ORCHESTRATION LAYER (Centered & Clean)
    %% ==========================================
    Coordinator["🧠 Context Router /<br/>Coordinator Agent"]:::coordinator
    
    FallbackBox["🔄 Resilient Fallback Chain:<br/>1. Primary: Gemini-3.5-Flash<br/>2. Gemini-Flash-Latest<br/>3. Gemini-3.1-Flash-Lite<br/>4. Gemini-2.5-Flash<br/>5. Deep Reasoning: Gemini-2.5-Pro"]:::fallbackBox

    %% Push fallback cleanly to the right
    Coordinator -.-> FallbackBox

    %% ==========================================
    %% 2. SPECIALIST SKILLS LAYER (Compressed Vertical Space)
    %% ==========================================
    %% Using compact arrows to tell the engine to bring the layers closer together
    Coordinator --> GroupA
    Coordinator --> GroupB
    Coordinator --> GroupC
    Coordinator --> GroupD

    subgraph SpecialistSkillsLayer ["2. SPECIALIST SKILLS LAYER (Activated on Demand)"]
        direction LR

        %% Sub-group A: Core Defense & Parsing
        subgraph GroupA ["A. Core Defense & Parsing"]
            direction TB
            S1["🔍 Skill 1: Image Content Guard<br>(Is Food Valid?)"]:::skill
            S2["🍳 Skill 2: Home-Cooked vs Restaurant<br>Classifier"]:::skill
            S3["🛡️ Skill 3: Witty Cop-Verdict Engine<br>(Police Verdict & 1 Action Item)"]:::skill
            S1 ~~~ S2 ~~~ S3
        end

        %% Sub-group B: Nutritional & Toxicological
        subgraph GroupB ["B. Nutrition & Toxicology"]
            direction TB
            S4["🌿 Skill 4: Micronutrient &<br>Antioxidant Estimator"]:::skill
            S5["🔥 Skill 5: Advanced Glycation End-Products<br>(AGEs) Detector"]:::skill
            S6["🫒 Skill 6: Lipid Peroxidation &<br>Seed Oil Hazard Analyst"]:::skill
            S4 ~~~ S5 ~~~ S6
        end

        %% Sub-group C: Physiological Alignment
        subgraph GroupC ["C. Physiological Alignment"]
            direction TB
            S7["🧘 Skill 7: Gut Mucosal Shield<br>(Neba-Neba Mucilage Hero Score)"]:::skill
            S8["🍱 Skill 8: User Traits Contextualizer<br>(Leftovers, Deep Fried, Polyphenols)"]:::skill
            S9["💪 Skill 9: Biometric Overlay Adjuster<br>(Sleep Deprived, Workout, Gut, Stress)"]:::skill
            S7 ~~~ S8 ~~~ S9
        end

        %% Sub-group D: Trend & Synthesis
        subgraph GroupD ["D. Trend & Synthesis"]
            direction TB
            S10["📊 Skill 10: Dietary Inflammatory Index (DII) Engine<br>(Score Evaluation)"]:::skill
            S11["✍️ Skill 11: Historic Trend Analyzer<br>"]:::skill
            S12["💾 Skill 12: Clinical Narrative Synthesizer<br>(Scientific Explanation)"]:::skill
            S10 ~~~ S11 ~~~ S12
        end
    end
    style SpecialistSkillsLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px
    style GroupA skillGroup
    style GroupB skillGroup
    style GroupC skillGroup
    style GroupD skillGroup

    %% ==========================================
    %% 3. DATA & KNOWLEDGE LAYER (Bottom)
    %% ==========================================
    GroupA --> DataLayer
    GroupB --> DataLayer
    GroupC --> DataLayer
    GroupD --> DataLayer

    subgraph DataLayer ["3. DATA & KNOWLEDGE LAYER"]
        direction LR
        DB1[("🗄️ Mount Sinai AGE DB<br>(STATIC_INGREDIENTS)")]:::db
        DB2[("📚 WHO Chronic Disease Index<br>(& Anti-Aging Literature)")]:::db
        DB3[("💾 User History Log DB<br>(& Logged Meal History)")]:::db
        DB1 ~~~ DB2 ~~~ DB3
    end
    style DataLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px

    %% Output
    DataLayer --> FinalOutput([📋 Output: Dynamic Clinical Report & Witty Chinese Polish Output]):::output
```
## Agents/Skills Specification

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
flowchart TD
    %% Global Light-Themed Styling Config
    classDef coordinator fill:#f3e8ff,stroke:#7c3aed,stroke-width:2px,color:#4c1d95,font-weight:bold;
    classDef fallbackBox fill:#eff6ff,stroke:#3b82f6,stroke-width:1px,stroke-dasharray: 4 4,color:#1e40af,font-size:11px;
    classDef skillGroup fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px,color:#1e293b,font-weight:bold;
    classDef skill fill:#ffffff,stroke:#64748b,stroke-width:1px,color:#334155,font-size:11px;
    classDef db fill:#f0fdf4,stroke:#16a34a,stroke-width:1.5px,color:#14532d;
    classDef output fill:#fef3c7,stroke:#d97706,stroke-width:2px,color:#92400e,font-weight:bold;

    %% --- USER INPUT TRIGGER ---
    Input([👤 User Uploads Meal Image + User Tags]) --> Coordinator

    %% ==========================================
    %% 1. ORCHESTRATION LAYER (Centered & Clean)
    %% ==========================================
    Coordinator["🧠 Context Router /<br/>Coordinator Agent"]:::coordinator
    
    FallbackBox["🔄 Resilient Fallback Chain:<br/>1. Primary: Gemini-3.5-Flash<br/>2. Gemini-Flash-Latest<br/>3. Gemini-3.1-Flash-Lite<br/>4. Gemini-2.5-Flash<br/>5. Deep Reasoning: Gemini-2.5-Pro"]:::fallbackBox

    %% Push fallback cleanly to the right
    Coordinator -.-> FallbackBox

    %% ==========================================
    %% 2. SPECIALIST SKILLS LAYER (Compressed Vertical Space)
    %% ==========================================
    %% Using compact arrows to tell the engine to bring the layers closer together
    Coordinator --> GroupA
    Coordinator --> GroupB
    Coordinator --> GroupC
    Coordinator --> GroupD

    subgraph SpecialistSkillsLayer ["2. SPECIALIST SKILLS LAYER (Activated on Demand)"]
        direction LR

        %% Sub-group A: Core Defense & Parsing
        subgraph GroupA ["A. Core Defense & Parsing"]
            direction TB
            S1["🔍 Skill 1: Image Content Guard<br>(Is Food Valid?)"]:::skill
            S2["🍳 Skill 2: Home-Cooked vs Restaurant<br>Classifier"]:::skill
            S3["🛡️ Skill 3: Witty Cop-Verdict Engine<br>(Police Verdict & 1 Action Item)"]:::skill
            S1 ~~~ S2 ~~~ S3
        end

        %% Sub-group B: Nutritional & Toxicological
        subgraph GroupB ["B. Nutrition & Toxicology"]
            direction TB
            S4["🌿 Skill 4: Micronutrient &<br>Antioxidant Estimator"]:::skill
            S5["🔥 Skill 5: Advanced Glycation End-Products<br>(AGEs) Detector"]:::skill
            S6["🫒 Skill 6: Lipid Peroxidation &<br>Seed Oil Hazard Analyst"]:::skill
            S4 ~~~ S5 ~~~ S6
        end

        %% Sub-group C: Physiological Alignment
        subgraph GroupC ["C. Physiological Alignment"]
            direction TB
            S7["🧘 Skill 7: Gut Mucosal Shield<br>(Neba-Neba Mucilage Hero Score)"]:::skill
            S8["🍱 Skill 8: User Traits Contextualizer<br>(Leftovers, Deep Fried, Polyphenols)"]:::skill
            S9["💪 Skill 9: Biometric Overlay Adjuster<br>(Sleep Deprived, Workout, Gut, Stress)"]:::skill
            S7 ~~~ S8 ~~~ S9
        end

        %% Sub-group D: Trend & Synthesis
        subgraph GroupD ["D. Trend & Synthesis"]
            direction TB
            S10["📊 Skill 10: Forensic Insights Builder<br>(Scientific Explanations)"]:::skill
            S11["✍️ Skill 11: Traditional Chinese<br>Native Polish Engine"]:::skill
            S12["💾 Skill 12: MCP DB Connector<br>(Metabolic Scoring API)"]:::skill
            S10 ~~~ S11 ~~~ S12
        end
    end
    style SpecialistSkillsLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px
    style GroupA skillGroup
    style GroupB skillGroup
    style GroupC skillGroup
    style GroupD skillGroup

    %% ==========================================
    %% 3. DATA & KNOWLEDGE LAYER (Bottom)
    %% ==========================================
    GroupA --> DataLayer
    GroupB --> DataLayer
    GroupC --> DataLayer
    GroupD --> DataLayer

    subgraph DataLayer ["3. DATA & KNOWLEDGE LAYER"]
        direction LR
        DB1[("🗄️ Mount Sinai AGE DB<br>(STATIC_INGREDIENTS)")]:::db
        DB2[("📚 WHO Chronic Disease Index<br>(& Anti-Aging Literature)")]:::db
        DB3[("💾 User History Log DB<br>(& Logged Meal History)")]:::db
        DB1 ~~~ DB2 ~~~ DB3
    end
    style DataLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px

    %% Output
    DataLayer --> FinalOutput([📋 Output: Dynamic Clinical Report & Witty Chinese Polish Output]):::output
```
```mermaid
flowchart TD
    %% Global Light-Themed Styling Config
    classDef coordinator fill:#f3e8ff,stroke:#7c3aed,stroke-width:2px,color:#4c1d95,font-weight:bold;
    classDef fallbackBox fill:#eff6ff,stroke:#3b82f6,stroke-width:1px,stroke-dasharray: 4 4,color:#1e40af,font-size:11px;
    classDef skillGroup fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px,color:#1e293b,font-weight:bold;
    classDef skill fill:#ffffff,stroke:#64748b,stroke-width:1px,color:#334155,font-size:11px;
    classDef db fill:#f0fdf4,stroke:#16a34a,stroke-width:1.5px,color:#14532d;
    classDef output fill:#fef3c7,stroke:#d97706,stroke-width:2px,color:#92400e,font-weight:bold;

    %% --- USER INPUT TRIGGER ---
    Input([👤 User Uploads Meal Image + User Tags]) --> Coordinator

    %% ==========================================
    %% 1. ORCHESTRATION LAYER (Super Compact)
    %% ==========================================
    Coordinator["🧠 Context Router /<br/>Coordinator Agent"]:::coordinator
    
    %% Use pure text formatting inside a single node to display the fallback chain concisely
    FallbackBox["🔄 Resilient Fallback Chain:<br/>1. Primary: Gemini-3.5-Flash<br/>2. Gemini-Flash-Latest<br/>3. Gemini-3.1-Flash-Lite<br/>4. Gemini-2.5-Flash<br/>5. Deep Reasoning: Gemini-2.5-Pro"]:::fallbackBox

    %% Push the fallback explanation box neatly to the right
    Coordinator -.-> FallbackBox

    %% ==========================================
    %% 2. SPECIALIST SKILLS LAYER (Perfectly Centered Below)
    %% ==========================================
    Coordinator ===> GroupA
    Coordinator ===> GroupB
    Coordinator ===> GroupC
    Coordinator ===> GroupD

    subgraph SpecialistSkillsLayer ["2. SPECIALIST SKILLS LAYER (Activated on Demand)"]
        direction LR

        %% Sub-group A: Core Defense & Parsing
        subgraph GroupA ["A. Core Defense & Parsing"]
            direction TB
            S1["🔍 Skill 1: Image Content Guard<br>(Is Food Valid?)"]:::skill
            S2["🍳 Skill 2: Home-Cooked vs Restaurant<br>Classifier"]:::skill
            S3["🛡️ Skill 3: Witty Cop-Verdict Engine<br>(Police Verdict & 1 Action Item)"]:::skill
            S1 ~~~ S2 ~~~ S3
        end

        %% Sub-group B: Nutritional & Toxicological
        subgraph GroupB ["B. Nutrition & Toxicology"]
            direction TB
            S4["🌿 Skill 4: Micronutrient &<br>Antioxidant Estimator"]:::skill
            S5["🔥 Skill 5: Advanced Glycation End-Products<br>(AGEs) Detector"]:::skill
            S6["🫒 Skill 6: Lipid Peroxidation &<br>Seed Oil Hazard Analyst"]:::skill
            S4 ~~~ S5 ~~~ S6
        end

        %% Sub-group C: Physiological Alignment
        subgraph GroupC ["C. Physiological Alignment"]
            direction TB
            S7["🧘 Skill 7: Gut Mucosal Shield<br>(Neba-Neba Mucilage Hero Score)"]:::skill
            S8["🍱 Skill 8: User Traits Contextualizer<br>(Leftovers, Deep Fried, Polyphenols)"]:::skill
            S9["💪 Skill 9: Biometric Overlay Adjuster<br>(Sleep Deprived, Workout, Gut, Stress)"]:::skill
            S7 ~~~ S8 ~~~ S9
        end

        %% Sub-group D: Trend & Synthesis
        subgraph GroupD ["D. Trend & Synthesis"]
            direction TB
            S10["📊 Skill 10: Forensic Insights Builder<br>(Scientific Explanations)"]:::skill
            S11["✍️ Skill 11: Traditional Chinese<br>Native Polish Engine"]:::skill
            S12["💾 Skill 12: MCP DB Connector<br>(Metabolic Scoring API)"]:::skill
            S10 ~~~ S11 ~~~ S12
        end
    end
    style SpecialistSkillsLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px
    style GroupA skillGroup
    style GroupB skillGroup
    style GroupC skillGroup
    style GroupD skillGroup

    %% ==========================================
    %% 3. DATA & KNOWLEDGE LAYER (Bottom)
    %% ==========================================
    GroupA --> DataLayer
    GroupB --> DataLayer
    GroupC --> DataLayer
    GroupD --> DataLayer

    subgraph DataLayer ["3. DATA & KNOWLEDGE LAYER"]
        direction LR
        DB1[("🗄️ Mount Sinai AGE DB<br>(STATIC_INGREDIENTS)")]:::db
        DB2[("📚 WHO Chronic Disease Index<br>(& Anti-Aging Literature)")]:::db
        DB3[("💾 User History Log DB<br>(& Logged Meal History)")]:::db
        DB1 ~~~ DB2 ~~~ DB3
    end
    style DataLayer fill:#f8fafc,cbd5e1,stroke-width:1.5px

    %% Output
    DataLayer --> FinalOutput([📋 Output: Dynamic Clinical Report & Witty Chinese Polish Output]):::output

```



```mermaid
flowchart TD
    %% Global Light-Themed Styling Config
    classDef coordinator fill:#f3e8ff,stroke:#7c3aed,stroke-width:2px,color:#4c1d95,font-weight:bold;
    classDef fallback fill:#eff6ff,stroke:#3b82f6,stroke-width:1.5px,stroke-dasharray: 4 4,color:#1e40af;
    classDef fallbackNode fill:#3b82f6,stroke:none,color:#ffffff,font-size:11px;
    classDef skillGroup fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px,color:#1e293b,font-weight:bold;
    classDef skill fill:#ffffff,stroke:#64748b,stroke-width:1px,color:#334155,font-size:11px;
    classDef db fill:#f0fdf4,stroke:#16a34a,stroke-width:1.5px,color:#14532d;
    classDef output fill:#fef3c7,stroke:#d97706,stroke-width:2px,color:#92400e,font-weight:bold;

    %% --- USER INPUT TRIGGER ---
    Input([👤 User Uploads Meal Image + User Tags]) --> Coordinator

    %% ==========================================
    %% 1. ORCHESTRATION & FALLBACK MATRIX (Top)
    %% ==========================================
    Coordinator["🧠 Context Router /<br/>Coordinator Agent"]:::coordinator
    
    subgraph FallbackPool ["Resilient Model Fallback Pool<br>(Low Latency Matrix)"]
        direction TB
        M1["Primary: Gemini-3.5-Flash"]:::fallbackNode -->|Fallback 1| M2["Gemini-Flash-Latest"]:::fallbackNode
        M2 -->|Fallback 2| M3["Gemini-3.1-Flash-Lite"]:::fallbackNode
        M3 -->|Fallback 3| M4["Gemini-2.5-Flash"]:::fallbackNode
        M4 -->|Fallback 4| M5["Deep Reasoning: Gemini-2.5-Pro"]:::fallbackNode
    end
    style FallbackPool fallback

    %% Hard Constraint: Force FallbackPool to stay strictly on the RIGHT of the Coordinator
    Coordinator -.-> FallbackPool

    %% ==========================================
    %% 2. SPECIALIST SKILLS LAYER (Middle)
    %% ==========================================
    %% Strong vertical anchoring to pull the skills layer directly under the Coordinator
    Coordinator ===> GroupA
    Coordinator ===> GroupB
    Coordinator ===> GroupC
    Coordinator ===> GroupD

    subgraph SpecialistSkillsLayer ["2. SPECIALIST SKILLS LAYER (Activated on Demand)"]
        direction LR

        %% Sub-group A: Core Defense & Parsing
        subgraph GroupA ["A. Core Defense & Parsing"]
            direction TB
            S1["🔍 Skill 1: Image Content Guard<br>(Is Food Valid?)"]:::skill
            S2["🍳 Skill 2: Home-Cooked vs Restaurant<br>Classifier"]:::skill
            S3["🛡️ Skill 3: Witty Cop-Verdict Engine<br>(Police Verdict & 1 Action Item)"]:::skill
            S1 ~~~ S2 ~~~ S3
        end

        %% Sub-group B: Nutritional & Toxicological
        subgraph GroupB ["B. Nutrition & Toxicology"]
            direction TB
            S4["🌿 Skill 4: Micronutrient &<br>Antioxidant Estimator"]:::skill
            S5["🔥 Skill 5: Advanced Glycation End-Products<br>(AGEs) Detector"]:::skill
            S6["🫒 Skill 6: Lipid Peroxidation &<br>Seed Oil Hazard Analyst"]:::skill
            S4 ~~~ S5 ~~~ S6
        end

        %% Sub-group C: Physiological Alignment
        subgraph GroupC ["C. Physiological Alignment"]
            direction TB
            S7["🧘 Skill 7: Gut Mucosal Shield<br>(Neba-Neba Mucilage Hero Score)"]:::skill
            S8["🍱 Skill 8: User Traits Contextualizer<br>(Leftovers, Deep Fried, Polyphenols)"]:::skill
            S9["💪 Skill 9: Biometric Overlay Adjuster<br>(Sleep Deprived, Workout, Gut, Stress)"]:::skill
            S7 ~~~ S8 ~~~ S9
        end

        %% Sub-group D: Trend & Synthesis
        subgraph GroupD ["D. Trend & Synthesis"]
            direction TB
            S10["📊 Skill 10: Forensic Insights Builder<br>(Scientific Explanations)"]:::skill
            S11["✍️ Skill 11: Traditional Chinese<br>Native Polish Engine"]:::skill
            S12["💾 Skill 12: MCP DB Connector<br>(Metabolic Scoring API)"]:::skill
            S10 ~~~ S11 ~~~ S12
        end
    end
    style SpecialistSkillsLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px
    style GroupA skillGroup
    style GroupB skillGroup
    style GroupC skillGroup
    style GroupD skillGroup

    %% ==========================================
    %% 3. DATA & KNOWLEDGE LAYER (Bottom)
    %% ==========================================
    GroupA --> DataLayer
    GroupB --> DataLayer
    GroupC --> DataLayer
    GroupD --> DataLayer

    subgraph DataLayer ["3. DATA & KNOWLEDGE LAYER"]
        direction LR
        DB1[("🗄️ Mount Sinai AGE DB<br>(STATIC_INGREDIENTS)")]:::db
        DB2[("📚 WHO Chronic Disease Index<br>(& Anti-Aging Literature)")]:::db
        DB3[("💾 User History Log DB<br>(& Logged Meal History)")]:::db
        DB1 ~~~ DB2 ~~~ DB3
    end
    style DataLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px

    %% Output
    DataLayer --> FinalOutput([📋 Output: Dynamic Clinical Report & Witty Chinese Polish Output]):::output
```

```mermaid
flowchart TD
    %% Global Light-Themed Styling Config
    classDef coordinator fill:#f3e8ff,stroke:#7c3aed,stroke-width:2px,color:#4c1d95,font-weight:bold;
    classDef fallback fill:#eff6ff,stroke:#3b82f6,stroke-width:1.5px,stroke-dasharray: 4 4,color:#1e40af;
    classDef fallbackNode fill:#3b82f6,stroke:none,color:#ffffff,font-size:11px;
    classDef skillGroup fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px,color:#1e293b,font-weight:bold;
    classDef skill fill:#ffffff,stroke:#64748b,stroke-width:1px,color:#334155,font-size:11px;
    classDef db fill:#f0fdf4,stroke:#16a34a,stroke-width:1.5px,color:#14532d;
    classDef output fill:#fef3c7,stroke:#d97706,stroke-width:2px,color:#92400e,font-weight:bold;

    %% --- USER INPUT TRIGGER ---
    Input([👤 User Uploads Meal Image + User Tags]) --> Coordinator

    %% ==========================================
    %% 1. ORCHESTRATION LAYER (Top & Centered)
    %% ==========================================
    Coordinator["🧠 Context Router /<br/>Coordinator Agent"]:::coordinator
    
    subgraph FallbackPool ["Resilient Model Fallback Pool (Low Latency Matrix)"]
        direction LR
        M1["Primary: Gemini-3.5-Flash"]:::fallbackNode -->|Fallback 1| M2["Gemini-Flash-Latest"]:::fallbackNode -->|Fallback 2| M3["Gemini-3.1-Flash-Lite"]:::fallbackNode -->|Fallback 3| M4["Gemini-2.5-Flash"]:::fallbackNode -->|Fallback 4| M5["Deep Reasoning: Gemini-2.5-Pro"]:::fallbackNode
    end
    style FallbackPool fallback

    %% Force FallbackPool to stay strictly on the RIGHT of the Coordinator
    Coordinator -.-> FallbackPool

    %% ==========================================
    %% 2. SPECIALIST SKILLS LAYER (Perfectly Underneath)
    %% ==========================================
    %% Strong vertical anchoring to pull the skills layer directly under the Coordinator
    Coordinator ===> GroupA
    Coordinator ===> GroupB
    Coordinator ===> GroupC
    Coordinator ===> GroupD

    subgraph SpecialistSkillsLayer ["2. SPECIALIST SKILLS LAYER (Activated on Demand)"]
        direction LR

        %% Sub-group A: Core Defense & Parsing
        subgraph GroupA ["A. Core Defense & Parsing"]
            direction TB
            S1["🔍 Skill 1: Image Content Guard<br>(Is Food Valid?)"]:::skill
            S2["🍳 Skill 2: Home-Cooked vs Restaurant<br>Classifier"]:::skill
            S3["🛡️ Skill 3: Witty Cop-Verdict Engine<br>(Police Verdict & 1 Action Item)"]:::skill
            S1 ~~~ S2 ~~~ S3
        end

        %% Sub-group B: Nutritional & Toxicological
        subgraph GroupB ["B. Nutrition & Toxicology"]
            direction TB
            S4["🌿 Skill 4: Micronutrient &<br>Antioxidant Estimator"]:::skill
            S5["🔥 Skill 5: Advanced Glycation End-Products<br>(AGEs) Detector"]:::skill
            S6["🫒 Skill 6: Lipid Peroxidation &<br>Seed Oil Hazard Analyst"]:::skill
            S4 ~~~ S5 ~~~ S6
        end

        %% Sub-group C: Physiological Alignment
        subgraph GroupC ["C. Physiological Alignment"]
            direction TB
            S7["🧘 Skill 7: Gut Mucosal Shield<br>(Neba-Neba Mucilage Hero Score)"]:::skill
            S8["🍱 Skill 8: User Traits Contextualizer<br>(Leftovers, Deep Fried, Polyphenols)"]:::skill
            S9["💪 Skill 9: Biometric Overlay Adjuster<br>(Sleep Deprived, Workout, Gut, Stress)"]:::skill
            S7 ~~~ S8 ~~~ S9
        end

        %% Sub-group D: Trend & Synthesis
        subgraph GroupD ["D. Trend & Synthesis"]
            direction TB
            S10["📊 Skill 10: Forensic Insights Builder<br>(Scientific Explanations)"]:::skill
            S11["✍️ Skill 11: Traditional Chinese<br>Native Polish Engine"]:::skill
            S12["💾 Skill 12: MCP DB Connector<br>(Metabolic Scoring API)"]:::skill
            S10 ~~~ S11 ~~~ S12
        end
    end
    style SpecialistSkillsLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px
    style GroupA skillGroup
    style GroupB skillGroup
    style GroupC skillGroup
    style GroupD skillGroup

    %% ==========================================
    %% 3. DATA & KNOWLEDGE LAYER (Bottom)
    %% ==========================================
    GroupA --> DataLayer
    GroupB --> DataLayer
    GroupC --> DataLayer
    GroupD --> DataLayer

    subgraph DataLayer ["3. DATA & KNOWLEDGE LAYER"]
        direction LR
        DB1[("🗄️ Mount Sinai AGE DB<br>(STATIC_INGREDIENTS)")]:::db
        DB2[("📚 WHO Chronic Disease Index<br>(& Anti-Aging Literature)")]:::db
        DB3[("💾 User History Log DB<br>(& Logged Meal History)")]:::db
        DB1 ~~~ DB2 ~~~ DB3
    end
    style DataLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px

    %% Output
    DataLayer --> FinalOutput([📋 Output: Dynamic Clinical Report & Witty Chinese Polish Output]):::output

```

```mermaid
flowchart TD
    %% Global Light-Themed Styling Config
    classDef coordinator fill:#f3e8ff,stroke:#7c3aed,stroke-width:2px,color:#4c1d95,font-weight:bold;
    classDef fallback fill:#eff6ff,stroke:#3b82f6,stroke-width:1.5px,stroke-dasharray: 4 4,color:#1e40af;
    classDef fallbackNode fill:#3b82f6,stroke:none,color:#ffffff,font-size:11px;
    classDef skillGroup fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px,color:#1e293b,font-weight:bold;
    classDef skill fill:#ffffff,stroke:#64748b,stroke-width:1px,color:#334155,font-size:11px;
    classDef db fill:#f0fdf4,stroke:#16a34a,stroke-width:1.5px,color:#14532d;
    classDef output fill:#fef3c7,stroke:#d97706,stroke-width:2px,color:#92400e,font-weight:bold;

    %% --- USER INPUT TRIGGER ---
    Input([👤 User Uploads Meal Image + User Tags]) --> Coordinator

    %% ==========================================
    %% 1. ORCHESTRATION LAYER (Centered Top, Fallback on the Right)
    %% ==========================================
    subgraph OrchestrationLayer ["1. ORCHESTRATION LAYER"]
        direction LR
        
        Coordinator["🧠 Context Router /<br/>Coordinator Agent"]:::coordinator
        
        subgraph FallbackPool ["Resilient Model Fallback Pool (Low Latency Matrix)"]
            direction LR
            M1["Primary: Gemini-3.5-Flash"]:::fallbackNode -->|Fallback 1| M2["Gemini-Flash-Latest"]:::fallbackNode -->|Fallback 2| M3["Gemini-3.1-Flash-Lite"]:::fallbackNode -->|Fallback 3| M4["Gemini-2.5-Flash"]:::fallbackNode -->|Fallback 4| M5["Deep Reasoning: Gemini-2.5-Pro"]:::fallbackNode
        end
        style FallbackPool fallback
    end
    style OrchestrationLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px
    
    Coordinator -.-> FallbackPool

    %% ==========================================
    %% 2. SPECIALIST SKILLS LAYER (Middle)
    %% ==========================================
    %% Explicitly linking Coordinator down to Skills to break the side-by-side push
    Coordinator --> GroupA
    Coordinator --> GroupB
    Coordinator --> GroupC
    Coordinator --> GroupD

    subgraph SpecialistSkillsLayer ["2. SPECIALIST SKILLS LAYER (Activated on Demand)"]
        direction LR

        %% Sub-group A: Core Defense & Parsing
        subgraph GroupA ["A. Core Defense & Parsing"]
            direction TB
            S1["🔍 Skill 1: Image Content Guard<br>(Is Food Valid?)"]:::skill
            S2["🍳 Skill 2: Home-Cooked vs Restaurant<br>Classifier"]:::skill
            S3["🛡️ Skill 3: Witty Cop-Verdict Engine<br>(Police Verdict & 1 Action Item)"]:::skill
            
            %% Force absolute vertical alignment via invisible links
            S1 ~~~ S2 ~~~ S3
        end

        %% Sub-group B: Nutritional & Toxicological
        subgraph GroupB ["B. Nutrition & Toxicology"]
            direction TB
            S4["🌿 Skill 4: Micronutrient &<br>Antioxidant Estimator"]:::skill
            S5["🔥 Skill 5: Advanced Glycation End-Products<br>(AGEs) Detector"]:::skill
            S6["🫒 Skill 6: Lipid Peroxidation &<br>Seed Oil Hazard Analyst"]:::skill
            
            %% Force absolute vertical alignment via invisible links
            S4 ~~~ S5 ~~~ S6
        end

        %% Sub-group C: Physiological Alignment
        subgraph GroupC ["C. Physiological Alignment"]
            direction TB
            S7["🧘 Skill 7: Gut Mucosal Shield<br>(Neba-Neba Mucilage Hero Score)"]:::skill
            S8["🍱 Skill 8: User Traits Contextualizer<br>(Leftovers, Deep Fried, Polyphenols)"]:::skill
            S9["💪 Skill 9: Biometric Overlay Adjuster<br>(Sleep Deprived, Workout, Gut, Stress)"]:::skill
            
            %% Force absolute vertical alignment via invisible links
            S7 ~~~ S8 ~~~ S9
        end

        %% Sub-group D: Trend & Synthesis
        subgraph GroupD ["D. Trend & Synthesis"]
            direction TB
            S10["📊 Skill 10: Forensic Insights Builder<br>(Scientific Explanations)"]:::skill
            S11["✍️ Skill 11: Traditional Chinese<br>Native Polish Engine"]:::skill
            S12["💾 Skill 12: MCP DB Connector<br>(Metabolic Scoring API)"]:::skill
            
            %% Force absolute vertical alignment via invisible links
            S10 ~~~ S11 ~~~ S12
        end
    end
    style SpecialistSkillsLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px
    style GroupA skillGroup
    style GroupB skillGroup
    style GroupC skillGroup
    style GroupD skillGroup

    %% Connections from Skills to Data Layer
    GroupA --> DataLayer
    GroupB --> DataLayer
    GroupC --> DataLayer
    GroupD --> DataLayer

    %% ==========================================
    %% 3. DATA & KNOWLEDGE LAYER (Bottom)
    %% ==========================================
    subgraph DataLayer ["3. DATA & KNOWLEDGE LAYER"]
        direction LR
        DB1[("🗄️ Mount Sinai AGE DB<br>(STATIC_INGREDIENTS)")]:::db
        DB2[("📚 WHO Chronic Disease Index<br>(& Anti-Aging Literature)")]:::db
        DB3[("💾 User History Log DB<br>(& Logged Meal History)")]:::db
        
        %% Force absolute horizontal alignment (left to right) via invisible links
        DB1 ~~~ DB2 ~~~ DB3
    end
    style DataLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px

    %% ==========================================
    %% OUTPUT TRIGGER
    %% ==========================================
    DataLayer --> FinalOutput([📋 Output: Dynamic Clinical Report & Witty Chinese Polish Output]):::output
```
```mermaid
flowchart TD
    %% Global Light-Themed Styling Config
    classDef coordinator fill:#f3e8ff,stroke:#7c3aed,stroke-width:2px,color:#4c1d95,font-weight:bold;
    classDef fallback fill:#eff6ff,stroke:#3b82f6,stroke-width:1.5px,stroke-dasharray: 4 4,color:#1e40af;
    classDef fallbackNode fill:#3b82f6,stroke:none,color:#ffffff,font-size:11px;
    classDef skillGroup fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px,color:#1e293b,font-weight:bold;
    classDef skill fill:#ffffff,stroke:#64748b,stroke-width:1px,color:#334155,font-size:11px;
    classDef db fill:#f0fdf4,stroke:#16a34a,stroke-width:1.5px,color:#14532d;
    classDef output fill:#fef3c7,stroke:#d97706,stroke-width:2px,color:#92400e,font-weight:bold;

    %% --- USER INPUT TRIGGER ---
    Input([👤 User Uploads Meal Image + User Tags]) --> Coordinator

    %% ==========================================
    %% 1. ORCHESTRATION LAYER (Top - Perfectly Centered)
    %% ==========================================
    subgraph OrchestrationLayer ["1. ORCHESTRATION LAYER"]
        direction TB
        
        Coordinator["🧠 Context Router /<br/>Coordinator Agent"]:::coordinator
        
        subgraph FallbackPool ["Resilient Model Fallback Pool (Low Latency Matrix)"]
            direction LR
            M1["Primary: Gemini-3.5-Flash"]:::fallbackNode -->|Fallback 1| M2["Gemini-Flash-Latest"]:::fallbackNode -->|Fallback 2| M3["Gemini-3.1-Flash-Lite"]:::fallbackNode -->|Fallback 3| M4["Gemini-2.5-Flash"]:::fallbackNode -->|Fallback 4| M5["Deep Reasoning: Gemini-2.5-Pro"]:::fallbackNode
        end
        style FallbackPool fallback
    end
    style OrchestrationLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px
    
    Coordinator -.-> FallbackPool

    %% Connections from Orchestration directly down to Specialist Skills
    Coordinator --> GroupA
    Coordinator --> GroupB
    Coordinator --> GroupC
    Coordinator --> GroupD

    %% ==========================================
    %% 2. SPECIALIST SKILLS LAYER (Middle)
    %% ==========================================
    subgraph SpecialistSkillsLayer ["2. SPECIALIST SKILLS LAYER (Activated on Demand)"]
        direction LR

        %% Sub-group A: Core Defense & Parsing
        subgraph GroupA ["A. Core Defense & Parsing"]
            direction TB
            S1["🔍 Skill 1: Image Content Guard<br>(Is Food Valid?)"]:::skill
            S2["🍳 Skill 2: Home-Cooked vs Restaurant<br>Classifier"]:::skill
            S3["🛡️ Skill 3: Witty Cop-Verdict Engine<br>(Police Verdict & 1 Action Item)"]:::skill
            
            %% Force absolute vertical alignment via invisible links
            S1 ~~~ S2 ~~~ S3
        end

        %% Sub-group B: Nutritional & Toxicological
        subgraph GroupB ["B. Nutrition & Toxicology"]
            direction TB
            S4["🌿 Skill 4: Micronutrient &<br>Antioxidant Estimator"]:::skill
            S5["🔥 Skill 5: Advanced Glycation End-Products<br>(AGEs) Detector"]:::skill
            S6["🫒 Skill 6: Lipid Peroxidation &<br>Seed Oil Hazard Analyst"]:::skill
            
            %% Force absolute vertical alignment via invisible links
            S4 ~~~ S5 ~~~ S6
        end

        %% Sub-group C: Physiological Alignment
        subgraph GroupC ["C. Physiological Alignment"]
            direction TB
            S7["🧘 Skill 7: Gut Mucosal Shield<br>(Neba-Neba Mucilage Hero Score)"]:::skill
            S8["🍱 Skill 8: User Traits Contextualizer<br>(Leftovers, Deep Fried, Polyphenols)"]:::skill
            S9["💪 Skill 9: Biometric Overlay Adjuster<br>(Sleep Deprived, Workout, Gut, Stress)"]:::skill
            
            %% Force absolute vertical alignment via invisible links
            S7 ~~~ S8 ~~~ S9
        end

        %% Sub-group D: Trend & Synthesis
        subgraph GroupD ["D. Trend & Synthesis"]
            direction TB
            S10["📊 Skill 10: Forensic Insights Builder<br>(Scientific Explanations)"]:::skill
            S11["✍️ Skill 11: Traditional Chinese<br>Native Polish Engine"]:::skill
            S12["💾 Skill 12: MCP DB Connector<br>(Metabolic Scoring API)"]:::skill
            
            %% Force absolute vertical alignment via invisible links
            S10 ~~~ S11 ~~~ S12
        end
    end
    style SpecialistSkillsLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px
    style GroupA skillGroup
    style GroupB skillGroup
    style GroupC skillGroup
    style GroupD skillGroup

    %% Connections from Skills to Data Layer
    GroupA --> DataLayer
    GroupB --> DataLayer
    GroupC --> DataLayer
    GroupD --> DataLayer

    %% ==========================================
    %% 3. DATA & KNOWLEDGE LAYER (Bottom)
    %% ==========================================
    subgraph DataLayer ["3. DATA & KNOWLEDGE LAYER"]
        direction LR
        DB1[("🗄️ Mount Sinai AGE DB<br>(STATIC_INGREDIENTS)")]:::db
        DB2[("📚 WHO Chronic Disease Index<br>(& Anti-Aging Literature)")]:::db
        DB3[("💾 User History Log DB<br>(& Logged Meal History)")]:::db
        
        %% Force absolute horizontal alignment (left to right) via invisible links
        DB1 ~~~ DB2 ~~~ DB3
    end
    style DataLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px

    %% ==========================================
    %% OUTPUT TRIGGER
    %% ==========================================
    DataLayer --> FinalOutput([📋 Output: Dynamic Clinical Report & Witty Chinese Polish Output]):::output
```
```mermaid
```
```mermaid
```


```mermaid
flowchart TD
    %% Global Light-Themed Styling Config
    classDef coordinator fill:#f3e8ff,stroke:#7c3aed,stroke-width:2px,color:#4c1d95,font-weight:bold;
    classDef fallback fill:#eff6ff,stroke:#3b82f6,stroke-width:1.5px,stroke-dasharray: 4 4,color:#1e40af;
    classDef fallbackNode fill:#3b82f6,stroke:none,color:#ffffff,font-size:11px;
    classDef skillGroup fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px,color:#1e293b,font-weight:bold;
    classDef skill fill:#ffffff,stroke:#64748b,stroke-width:1px,color:#334155,font-size:11px;
    classDef db fill:#f0fdf4,stroke:#16a34a,stroke-width:1.5px,color:#14532d;
    classDef output fill:#fef3c7,stroke:#d97706,stroke-width:2px,color:#92400e,font-weight:bold;
    classDef layerBox fill:#ffffff,stroke:#e2e8f0,stroke-width:2px,color:#0f172a,font-weight:bold;

    %% --- USER INPUT TRIGGER ---
    Input([👤 User Uploads Meal Image + User Tags]) --> Coordinator

    %% ==========================================
    %% 1. ORCHESTRATION LAYER (Top)
    %% ==========================================
    subgraph OrchestrationLayer ["1. ORCHESTRATION LAYER"]
        direction LR
        
        Coordinator["🧠 Context Router /<br/>Coordinator Agent"]:::coordinator
        
        subgraph FallbackPool ["Resilient Model Fallback Pool (Low Latency Matrix)"]
            direction TB
            M1["Primary: Gemini-3.5-Flash"]:::fallbackNode -->|Fallback 1| M2["Gemini-Flash-Latest"]:::fallbackNode
            M2 -->|Fallback 2| M3["Gemini-3.1-Flash-Lite"]:::fallbackNode
            M3 -->|Fallback 3| M4["Gemini-2.5-Flash"]:::fallbackNode
            M4 -->|Fallback 4| M5["Deep Reasoning: Gemini-2.5-Pro"]:::fallbackNode
        end
        style FallbackPool fallback
    end
    style OrchestrationLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px
    
    Coordinator -.-> FallbackPool

    %% Connections from Orchestration to Specialist Skills
    Coordinator --> GroupA
    Coordinator --> GroupB
    Coordinator --> GroupC
    Coordinator --> GroupD

    %% ==========================================
    %% 2. SPECIALIST SKILLS LAYER (Middle)
    %% ==========================================
    subgraph SpecialistSkillsLayer ["2. SPECIALIST SKILLS LAYER (Activated on Demand)"]
        direction LR

        %% Sub-group A: Core Defense & Parsing
        subgraph GroupA ["A. Core Defense & Parsing"]
            direction TB
            S1["🔍 Skill 1: Image Content Guard<br>(Is Food Valid?)"]:::skill
            S2["🍳 Skill 2: Home-Cooked vs Restaurant<br>Classifier"]:::skill
            S3["🛡️ Skill 3: Witty Cop-Verdict Engine<br>(Police Verdict & 1 Action Item)"]:::skill
        end

        %% Sub-group B: Nutritional & Toxicological
        subgraph GroupB ["B. Nutrition & Toxicology"]
            direction TB
            S4["🌿 Skill 4: Micronutrient &<br>Antioxidant Estimator"]:::skill
            S5["🔥 Skill 5: Advanced Glycation End-Products<br>(AGEs) Detector"]:::skill
            S6["🫒 Skill 6: Lipid Peroxidation &<br>Seed Oil Hazard Analyst"]:::skill
        end

        %% Sub-group C: Physiological Alignment
        subgraph GroupC ["C. Physiological Alignment"]
            direction TB
            S7["🧘 Skill 7: Gut Mucosal Shield<br>(Neba-Neba Mucilage Hero Score)"]:::skill
            S8["🍱 Skill 8: User Traits Contextualizer<br>(Leftovers, Deep Fried, Polyphenols)"]:::skill
            S9["💪 Skill 9: Biometric Overlay Adjuster<br>(Sleep Deprived, Workout, Gut, Stress)"]:::skill
        end

        %% Sub-group D: Trend & Synthesis
        subgraph GroupD ["D. Trend & Synthesis"]
            direction TB
            S10["📊 Skill 10: Forensic Insights Builder<br>(Scientific Explanations)"]:::skill
            S11["✍️ Skill 11: Traditional Chinese<br>Native Polish Engine"]:::skill
            S12["💾 Skill 12: MCP DB Connector<br>(Metabolic Scoring API)"]:::skill
        end
    end
    style SpecialistSkillsLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px
    style GroupA skillGroup
    style GroupB skillGroup
    style GroupC skillGroup
    style GroupD skillGroup

    %% Connections from Skills to Data Layer
    GroupA --> DataLayer
    GroupB --> DataLayer
    GroupC --> DataLayer
    GroupD --> DataLayer

    %% ==========================================
    %% 3. DATA & KNOWLEDGE LAYER (Bottom)
    %% ==========================================
    subgraph DataLayer ["3. DATA & KNOWLEDGE LAYER"]
        direction LR
        DB1[("🗄️ Mount Sinai AGE DB<br>(STATIC_INGREDIENTS)")]:::db
        DB2[("📚 WHO Chronic Disease Index<br>(& Anti-Aging Literature)")]:::db
        DB3[("💾 User History Log DB<br>(& Logged Meal History)")]:::db
    end
    style DataLayer fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px

    %% ==========================================
    %% OUTPUT TRIGGER
    %% ==========================================
    DataLayer --> FinalOutput([📋 Output: Dynamic Clinical Report & Witty Chinese Polish Output]):::output
```
```mermaid
flowchart TD
    %% Global Styling Config
    classDef layerTitle fill:#1e293b,stroke:#334155,stroke-width:2px,color:#f8fafc,font-weight:bold;
    classDef coordinator fill:#0f172a,stroke:#3b82f6,stroke-width:2px,color:#f8fafc,font-weight:bold;
    classDef fallback fill:#1e1b4b,stroke:#818cf8,stroke-dasharray: 5 5,color:#e0e7ff;
    classDef skillGroup fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px,color:#1e293b,font-weight:bold;
    classDef skill fill:#ffffff,stroke:#64748b,stroke-width:1px,color:#334155,font-size:11px;
    classDef db fill:#f1f5f9,stroke:#94a3b8,stroke-width:1.5px,color:#1e293b;
    classDef output fill:#22c55e,stroke:#15803d,stroke-width:2px,color:#ffffff,font-weight:bold;

    %% --- USER INPUT TRIGGER ---
    Input([User Uploads Meal Image + User Tags]) --> Coordinator

    %% ==========================================
    %% 1. ORCHESTRATION LAYER (Top)
    %% ==========================================
    subgraph OrchestrationLayer ["1. ORCHESTRATION LAYER"]
        direction LR
        
        Coordinator["Context Router / Coordinator Agent"]
        
        subgraph FallbackPool ["Resilient Model Fallback Pool (Low Latency Matrix)"]
            direction LR
            M1["Gemini-3.5-Flash"] -->|Fallback 1| M2["Gemini-Flash-Latest"]
            M2 -->|Fallback 2| M3["Gemini-3.1-Flash-Lite"]
            M3 -->|Fallback 3| M4["Gemini-2.5-Flash"]
            M4 -->|Fallback 4| M5["Gemini-2.5-Pro"]
        end
    end
    
    Coordinator <--> FallbackPool

    %% Connections from Orchestration to Specialist Skills
    Coordinator --> SpecialistSkillsLayer

    %% ==========================================
    %% 2. SPECIALIST SKILLS LAYER (Middle)
    %% ==========================================
    subgraph SpecialistSkillsLayer ["2. SPECIALIST SKILLS LAYER"]
        direction TB

        %% Sub-group A: Core Defense & Parsing
        subgraph GroupA ["A. Core Defense & Parsing"]
            direction TB
            S1["Skill 1: Image Content Guard<br>(Is Food Valid?)"]
            S2["Skill 2: Home-Cooked vs Restaurant<br>Classifier"]
            S3["Skill 3: Witty Cop-Verdict Engine<br>(Police Verdict & 1 Action Item)"]
        end

        %% Sub-group B: Nutritional & Toxicological
        subgraph GroupB ["B. Nutrition & Toxicology"]
            direction TB
            S4["Skill 4: Micronutrient &<br>Antioxidant Estimator"]
            S5["Skill 5: Advanced Glycation End-Products<br>(AGEs) Detector"]
            S6["Skill 6: Lipid Peroxidation &<br>Seed Oil Hazard Analyst"]
        end

        %% Sub-group C: Physiological Alignment
        subgraph GroupC ["C. Physiological Alignment"]
            direction TB
            S7["Skill 7: Gut Mucosal Shield<br>(Neba-Neba Mucilage Hero Score)"]
            S8["Skill 8: User Traits Contextualizer<br>(Leftovers, Deep Fried, Polyphenols)"]
            S9["Skill 9: Biometric Overlay Adjuster<br>(Sleep Deprived, Workout, Gut, Stress)"]
        end

        %% Sub-group D: Trend & Synthesis
        subgraph GroupD ["D. Trend & Synthesis"]
            direction TB
            S10["Skill 10: Forensic Insights Builder<br>(Scientific Explanations)"]
            S11["Skill 11: Traditional Chinese<br>Native Polish Engine"]
            S12["Skill 12: MCP DB Connector<br>(Metabolic Scoring API)"]
        end
    end

    %% ==========================================
    %% 3. DATA & KNOWLEDGE LAYER (Bottom)
    %% ==========================================
    SpecialistSkillsLayer --> DataLayer

    subgraph DataLayer ["3. DATA & KNOWLEDGE LAYER"]
        direction LR
        DB1[("Local MCP DB<br>(STATIC_INGREDIENTS)")]
        DB2[("WHO Guidelines / Medical<br>& Anti-Aging Literature")]
        DB3[("User Context Profiles<br>& Logged Meal History")]
    end

    %% ==========================================
    %% OUTPUT TRIGGER
    %% ==========================================
    DataLayer --> FinalOutput([Dynamic Clinical Report & Witty Chinese Polish Output])

    %% Apply Styles
    style OrchestrationLayer fill:#f8fafc,stroke:#334155,stroke-width:1.5px
    style SpecialistSkillsLayer fill:#f8fafc,stroke:#334155,stroke-width:1.5px
    style DataLayer fill:#f8fafc,stroke:#334155,stroke-width:1.5px
    
    style Coordinator coordinator
    style FallbackPool fallback
    style M1 fill:#4f46e5,color:#ffffff,stroke:none
    style M2 fill:#4f46e5,color:#ffffff,stroke:none
    style M3 fill:#4f46e5,color:#ffffff,stroke:none
    style M4 fill:#4f46e5,color:#ffffff,stroke:none
    style M5 fill:#4f46e5,color:#ffffff,stroke:none

    style GroupA skillGroup
    style GroupB skillGroup
    style GroupC skillGroup
    style GroupD skillGroup

    style S1 skill
    style S2 skill
    style S3 skill
    style S4 skill
    style S5 skill
    style S6 skill
    style S7 skill
    style S8 skill
    style S9 skill
    style S10 skill
    style S11 skill
    style S12 skill

    style DB1 db
    style DB2 db
    style DB3 db
    style FinalOutput output
```
```mermaid
[ USER UPLOADS MEAL IMAGE + DECLARES TRAITS ]
                                       │
                                       ▼
       ┌───────────────────────────────────────────────────────────────┐
       │     1. UNIVERSAL ORCHESTRATOR & CONTEXT ROUTER AGENT          │
       │                                                               │
       │  • Primary: models/gemini-3.5-flash                           │
       │  • Resilient Model Fallback Pool (Low-Latency Retries):       │
       │    gemini-flash-latest ➔ gemini-3.1-flash-lite ➔              │
       │    gemini-2.5-flash ➔ gemini-2.5-pro                          │
       └───────────────────────────────┬───────────────────────────────┘
                                       │
                    Dynamic Evaluation & Condition Matching
                                       │
                                       ▼
       ┌───────────────────────────────────────────────────────────────┐
       │     2. DYNAMIC SKILL INJECTION GRID (Zero-Latency Context)    │
       │                                                               │
       │   [CULINARY & OXIDATIVE SKILLS]    [CHRONO-NUTRITIONAL SKILLS]│
       │   • Seed Oil Peroxidation Detector • Circadian Sleep Depress  │
       │   • Deep-Fried AGEs Modulator      • Late-Night Metabolism    │
       │   • Polyphenol Defense Booster     • Alcohol Recovery Path    │
       │                                                               │
       │   [GUT BARRIER & MUCOSAL SKILLS]   [CLINICAL BIOMARKER SKILLS]│
       │   • Neba-Neba Mucosal Shielding    • Glycemic Peak Regulator  │
       │   • Histamine Accumulation Tracker • Cortisol-Stress Damper   │
       │   • Preservative Permeability Rule • Post-Workout Window      │
       └───────────────────────────────┬───────────────────────────────┘
                                       │
                     Fetches Ground Truth Evidence Base
                                       │
                                       ▼
       ┌───────────────────────────────────────────────────────────────┐
       │     3. MODEL CONTEXT PROTOCOL (MCP) INTEROPERABILITY          │
       │                                                               │
       │  • MCP Tool: ingredient_inflammation_db (Low-latency check)   │
       │  • Ground-Truth Database: STATIC_INGREDIENTS (Curated items)  │
       └───────────────────────────────┬───────────────────────────────┘
                                       │
                Consolidates into Single Structural JSON Output
                                       │
                                       ▼
                    [ POLISHED NATIVE USER REVEAL / VERDICT ]
```
```mermaid
graph TD
    %% User Inputs Layer %%
    subgraph Inputs ["User Input Signals"]
        A1["Meal Photo (Image Content)"]
        A2["User Biometric Tags (Post-Workout, Sleep Deprived, Gut Sensitive, Stress)"]
        A3["User Meal Traits (Seed Oil, Deep Fried, Polyphenol Rich, Leftovers)"]
    end

    %% Agent Coordinator Layer %%
    subgraph CoreAgent ["InflameCop Coordinator (Single-Agent Core)"]
        B1["Context Router & Orchestrator"]
        B2["Resilient Model Pool (Dynamic Fallback Loop)"]
        
        B1 --> B2
        B2 --> C1("1. Gemini 3.5 Flash (Primary)")
        B2 --> C2("2. Gemini Flash Latest (Backup)")
        B2 --> C3("3. Gemini 3.1 Flash-Lite (Low Latency)")
        B2 --> C4("4. Gemini 2.5 Flash (Compatibility)")
        B2 --> C5("5. Gemini 2.5 Pro (Deep Clinical Logic)")
    end

    Inputs --> B1

    %% Dynamic Skill Dispatcher %%
    B2 -->|On-Demand Context Injection| D["Dynamic Skill Dispatch Layer"]

    %% Grouped Skills Grid (Top-to-Bottom, Left-to-Right layout) %%
    subgraph Skills ["Modular Skills (Grouped to prevent infinite horizontal expansion)"]
        
        subgraph GroupA ["A. Ingest & Safety Safeguards"]
            S1["Skill 1: Non-Edible Shield (Is Food Filter)"]
            S2["Skill 2: Culinary Vision Perception"]
            S3["Skill 3: Kitchen Context Detector (Home vs Restaurant)"]
        end
        
        subgraph GroupB ["B. Nutrient & Lipid Grading"]
            S4["Skill 4: Seed Oil & Peroxidation Penalty"]
            S5["Skill 5: Clean Fats & EVOO Credit Boost"]
            S6["Skill 6: Biochemical Forensic Analysis (AGEs)"]
        end

        subgraph GroupC ["C. Chrono-Nutrition & Stress Tuning"]
            S7["Skill 7: Circadian Sympathetic Relief (Stress)"]
            S8["Skill 8: Melatonin Syncing (Late Night)"]
            S9["Skill 9: Golden Recovery Window (Post-Workout)"]
        end

        subgraph GroupD ["D. Gut Barrier & Witty Output"]
            S10["Skill 10: Neba-Neba Slimy Gut Shield"]
            S11["Skill 11: Gut Mucosa Repair (Gut Sensitive)"]
            S12["Skill 12: Witty Cop Verdict & Native Translation"]
        end
    end

    D --> GroupA
    D --> GroupB
    D --> GroupC
    D --> GroupD

    %% Output Synthesis Layer %%
    subgraph Output ["Anti-Aging Output Payload (Structured JSON)"]
        E1["Anti-Inflammatory Score (0-100)"]
        E2["Molecular Forensic Insights (AGEs, Gut Permeability)"]
        E3["Dual-Language Sharp Police Verdict (English + Witty Traditional Chinese)"]
    end

    GroupA --> Output
    GroupB --> Output
    GroupC --> Output
    GroupD --> Output

    %% Node Styling for Visual Rhythm %%
    classDef mainNode fill:#1e293b,stroke:#3b82f6,stroke-width:2px,color:#f8fafc;
    classDef skillNode fill:#0f172a,stroke:#10b981,stroke-width:1.5px,color:#f1f5f9;
    classDef modelNode fill:#1e1b4b,stroke:#a855f7,stroke-width:1.5px,color:#f5f3ff;
    
    class B1,B2,D,E1,E2,E3 mainNode;
    class S1,S2,S3,S4,S5,S6,S7,S8,S9,S10,S11,S12 skillNode;
    class C1,C2,C3,C4,C5 modelNode;
```

```mermaid

graph TD
    %% Define Light-Themed Styles for GitHub
    classDef main fill:#f3e8ff,stroke:#7C3AED,stroke-width:2px,color:#4c1d95;
    classDef skill fill:#e0f2fe,stroke:#0284c7,stroke-width:1.5px,color:#0369a1;
    classDef context fill:#d1fae5,stroke:#059669,stroke-width:1.5px,color:#065f46;
    classDef state fill:#fee2e2,stroke:#dc2626,stroke-width:1.5px,color:#991b1b;
    classDef report fill:#fef3c7,stroke:#d97706,stroke-width:2px,color:#92400e;
    classDef group fill:#f8fafc,stroke:#cbd5e1,stroke-width:1px,color:#64748b;

    %% User Input
    User[👤 貼入食物照片 & 勾選標籤] --> Core

    %% Single Agent Core
    subgraph CoreAgent [單一通用智能體 Single Agent Core]
        Core["🧠 InflameCop 通用 Agent 核心<br/>Powered by Gemini 3.5 Flash"]
    end
    class Core main;
    class CoreAgent group;

    %% Dynamic Skills Registry 
    %% 將巢狀子圖平鋪或透過節點連線修正，確保 GitHub 解析成功
    subgraph MealContext [外食/家常情境標籤 Skills]
        S3[⚠️ 3. 種子油危害與脂質氧化分析]:::context
        S4[🫒 4. 優質冷壓油品加分最佳化]:::context
        S5[🔥 5. 高溫油炸 AGEs 毒性計算]:::context
        S6[🌿 6. 豐富多酚抗氧化補償計算]:::context
        S7[🍱 7. 剩菜與組胺累積免疫耐受度]:::context
        S8[🥫 8. 罐頭與加工防腐劑/雙酚A負荷]:::context
    end
    class MealContext group;

    subgraph Biometrics [生理與生物特徵標籤 Skills]
        S9[💪 9. 運動後黃金期蛋白質合成修復]:::state
        S10[😴 10. 熬夜高皮質醇糖盾防護]:::state
        S11[🌙 11. 深夜褪黑素與消化減緩警戒]:::state
        S12[🧘 12. 腸胃敏感黏膜保護與 neba-neba 加分]:::state
    end
    class Biometrics group;

    subgraph BaseSkills [基礎防禦與判定 Skills]
        S1[🔍 1. 非食物圖像防禦與過濾]:::skill
        S2[🍳 2. 外食與家常 Risk 梯度評分]:::skill
    end
    class BaseSkills group;

    %% Relationships & Flow (修正連線至具體第一個節點，避免 GitHub 報錯)
    Core -->|1. 影像校驗| S1
    Core -->|2. 環境判定| S2
    Core -->|3. 動態加載情境| S3
    Core -->|4. 動態加載生理狀態| S9

    %% Aggregated Output Flow
    S1 & S2 & S3 & S4 & S5 & S6 & S7 & S8 & S9 & S10 & S11 & S12 --> Combine[智能綜合輸出]
    Combine --> Output[📋 5秒極速發炎警察臨床報告]:::report
    class Combine main;
```

```mermaid
graph TD
    %% Define Light-Themed Styles
    classDef coordinator fill:#f3e8ff,stroke:#a855f7,stroke-width:2px,color:#4a044e;
    classDef registryGroup fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px,color:#475569;
    classDef rowGroup fill:#f1f5f9,stroke:#e2e8f0,stroke-width:1px,color:#64748b;
    classDef skill fill:#e0f2fe,stroke:#0284c7,stroke-width:1.5px,color:#0369a1;
    classDef external fill:#d1fae5,stroke:#059669,stroke-width:1.5px,color:#065f46;

    %% Orchestration Layer
    subgraph Orchestration_Layer [Orchestration Layer]
        Coordinator["🤖 CONTEXT ROUTER & COORDINATOR AGENT<br/>(Gemini 3.5-Flash)"]
    end
    class Coordinator coordinator;

    %% Dynamic Skills Registry (Light Background)
    subgraph Skills_Registry [Dynamic Skill Registry - Activated on Demand]
        
        subgraph Row1 [1. Core Defense & Parsing]
            S1["🛡️ 1. Security Guard & Input Validator"]
            S2["👁️ 2. Computer Vision Ingredient Parser"]
            S3["🩺 3. Chronic Disease Guidelines Matcher"]
            S4["🔥 4. Glycation Risk Estimator (AGEs)"]
        end
        
        subgraph Row2 [2. Clinical Metrics & Alignment]
            S5["📊 5. Dietary Inflammatory Index (DII) Engine"]
            S6["⏰ 6. Chrono-Nutrition & Circadian Alignment"]
            S7["🧬 7. Personal Biomarker Profiler"]
            S8["🦠 8. Gut Microbiome Symbiosis Matcher"]
        end
        
        subgraph Row3 [3. Trends & Synthesis]
            S9["🌿 9. Antioxidant & Phytonutrient Evaluator"]
            S10["💧 10. Hydration & Electrolyte Balancer"]
            S11["📈 11. Historic Trend Analyzer"]
            S12["✍️ 12. Clinical Narrative Synthesizer"]
        end
        
    end
    class S1,S2,S3,S4,S5,S6,S7,S8,S9,S10,S11,S12 skill;
    class Row1,Row2,Row3 rowGroup;

    %% Data & External Tool Integration Layer (MCP / SDK)
    subgraph External_Layer [Data & Tool Integration Layer]
        GenAI["⚡ Google GenAI SDK"]
        WHODB["📚 WHO Chronic Disease Index"]
        AGEDB["🧪 Mount Sinai AGE Database"]
        HistoryDB["💾 InflameCop Historic DB"]
    end
    class GenAI,WHODB,AGEDB,HistoryDB external;

    %% Relationships & Flow
    Coordinator -->|1. Detects Intent & Loads| Skills_Registry
    
    %% Dynamic Execution Bindings
    S1 -.->|Cleans & Validates| Coordinator
    S2 -.->|Extracts Culinary Features| Coordinator
    S3 -.-> WHODB
    S4 -.-> AGEDB
    S5 -.->|Calculates Inflammatory Potential| Coordinator
    S11 -.-> HistoryDB
    
    %% Final Synthesis Flow
    Skills_Registry -->|2. Aggregated Payloads| Coordinator
    Coordinator -->|3. Final Structured Synthesis| GenAI

    %% Apply Style Groups
    class Skills_Registry registryGroup;
    class External_Layer registryGroup;
```
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
```mermaid

graph TD
    %% Define Styles
    classDef coordinator fill:#4c1d95,stroke:#c084fc,stroke-width:2px,color:#fff;
    classDef skillGroup fill:#0f172a,stroke:#334155,stroke-width:1px,color:#94a3b8;
    classDef skill fill:#1e293b,stroke:#38bdf8,stroke-width:1.5px,color:#f8fafc;
    classDef external fill:#022c22,stroke:#10b981,stroke-width:1.5px,color:#ecfdf5;

    %% Orchestration Layer
    subgraph Orchestration_Layer [Orchestration Layer]
        Coordinator["🤖 CONTEXT ROUTER & COORDINATOR AGENT<br/>(Gemini 3.5-Flash)"]
    end
    class Coordinator coordinator;

    %% Dynamic Skills Registry
    subgraph Skills_Registry [Dynamic Skill Registry - Activated on Demand]
        S1["🛡️ 1. Security Guard & Input Validator"]
        S2["👁️ 2. Computer Vision Ingredient Parser"]
        S3["🩺 3. Chronic Disease Guidelines Matcher"]
        S4["🔥 4. Glycation Risk Estimator (AGEs)"]
        S5["📊 5. Dietary Inflammatory Index (DII) Engine"]
        S6["⏰ 6. Chrono-Nutrition & Circadian Alignment"]
        S7["🧬 7. Personal Biomarker Profiler"]
        S8["🦠 8. Gut Microbiome Symbiosis Matcher"]
        S9["🌿 9. Antioxidant & Phytonutrient Evaluator"]
        S10["💧 10. Hydration & Electrolyte Balancer"]
        S11["📈 11. Historic Trend Analyzer"]
        S12["✍️ 12. Clinical Narrative Synthesizer"]
    end
    class S1,S2,S3,S4,S5,S6,S7,S8,S9,S10,S11,S12 skill;

    %% Data & External Tool Integration Layer (MCP / SDK)
    subgraph External_Layer [Data & Tool Integration Layer]
        GenAI["⚡ Google GenAI SDK"]
        WHODB["📚 WHO Chronic Disease Index"]
        AGEDB["🧪 Mount Sinai AGE Database"]
        HistoryDB["💾 InflameCop Historic DB"]
    end
    class GenAI,WHODB,AGEDB,HistoryDB external;

    %% Relationships & Flow
    Coordinator -->|1. Detects Intent & Loads| Skills_Registry
    
    %% Dynamic Execution Bindings
    S1 -.->|Cleans & Validates| Coordinator
    S2 -.->|Extracts Culinary Features| Coordinator
    S3 -.-> WHODB
    S4 -.-> AGEDB
    S5 -.->|Calculates Inflammatory Potential| Coordinator
    S11 -.-> HistoryDB
    
    %% Final Synthesis Flow
    Skills_Registry -->|2. Aggregated Payloads| Coordinator
    Coordinator -->|3. Final Structured Synthesis| GenAI

    %% Apply Style Groups
    class Skills_Registry skillGroup;
    class External_Layer skillGroup;
```
```mermaid
graph TD
    classDef main fill:#7C3AED,stroke:#9F67FF,stroke-width:2px,color:#fff;
    classDef skill fill:#1F2937,stroke:#4B5563,stroke-width:1px,color:#E5E7EB;
    classDef state fill:#1E3A8A,stroke:#3B82F6,stroke-width:1.5px,color:#93C5FD;
    classDef context fill:#064E3B,stroke:#10B981,stroke-width:1.5px,color:#A7F3D0;
    classDef report fill:#0F172A,stroke:#F59E0B,stroke-width:2px,color:#FBBF24;

    User[👤 貼入食物照片 & 勾選標籤] --> Core[🧠 InflameCop 通用 Agent 核心<br/>Powered by Gemini 3.5 Flash]

    subgraph CoreAgent [單一通用智能體 (Single Agent Core)]
        Core
    end

    subgraph DynamicSkills [12 個動態載入的臨床分析技能 (Dynamic Skills)]
        S1[🔍 1. 非食物圖像防禦與過濾]:::skill
        S2[🍳 2. 外食與家常 Risk 梯度評分]:::skill
        
        subgraph MealContext [外食/家常情境標籤 Skills]
            S3[⚠️ 3. 種子油危害與脂質氧化分析]:::context
            S4[🫒 4. 優質冷壓油品加分最佳化]:::context
            S5[🔥 5. 高溫油炸 AGEs 毒性計算]:::context
            S6[🌿 6. 豐富多酚抗氧化補償計算]:::context
            S7[🍱 7. 剩菜與組胺累積免疫耐受度]:::context
            S8[🥫 8. 罐頭與加工防腐劑/雙酚A負荷]:::context
        end

        subgraph Biometrics [生理與生物特徵標籤 Skills]
            S9[💪 9. 運動後黃金期蛋白質合成修復]:::state
            S10[😴 10. 熬夜高皮質醇糖盾防護]:::state
            S11[🌙 11. 深夜褪黑素與消化減緩警戒]:::state
            S12[🧘 12. 腸胃敏感黏膜保護與 neba-neba 加分]:::state
        end
    end

    Core -->|1. 影像校驗| S1
    Core -->|2. 環境判定| S2
    Core -->|3. 動態加載情境| MealContext
    Core -->|4. 動態加載生理狀態| Biometrics

    DynamicSkills -->|智能綜合輸出| Output[📋 5秒極速發炎警察臨床報告]:::report

    class Core main;
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

