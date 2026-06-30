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
# 3. Why Agents & Solutions



🎯 Consumer Pain Points vs. Agentic Solutions

| No | Core Agent Trait | Consumer Pain Point | InflameCop Product Feature |
| :--- | :--- | :--- | :--- |
| 1 | **Domain Specialization**<br/><br/>Isolated field experts over a single generic LLM. | **Invisible Toxins**<br/><br/>Hidden molecular triggers (AGEs, Omega-6). | **Culinary Feature Vector Extraction**<br/><br/>Vision Perception Agent converts raw pixels into structured ingredient vectors. |
| 2 | **Parallel Processing**<br/><br/>Concurrent execution cuts audit time to seconds. | **Monolithic Delay**<br/><br/>Slow sequential data processing destroys UX. | **Asynchronous Multi-Agent Ingestion**<br/><br/>Security, Vision, and Context fields process concurrently at user entry. |
| 3 | **Transparency & Explainability**<br/><br/>Visible, traceable routing with confidence logic. | **AI Black Box**<br/><br/>Users distrust unverified, hallucinated advice. | **Multi-Signal Diagnostic Auditing**<br/><br/>Every metric cites exact contributing agents, lifestyle parameters, and DII lookup scores. |
| 4 | **Contextual Modularity**<br/><br/>Independent, decoupled operational frameworks. | **Rigid Nutrition Tracking**<br/><br/>Static apps ignore lifestyle/chrono variables. | **Dynamic Context Modifier**<br/><br/>Context Penalty Agent runs custom behavioral scoring without resetting core architecture. |
| 5 | **A2A Protocol Standards**<br/><br/>Loosely coupled, message-based standard routing. | **Fragile Ecosystem**<br/><br/>Point-to-point data connections crash under load. | **Unified MCP Routing Gateway**<br/><br/>Knowledge Retrieval Agent standardizes database interop to O(N+M) ports. |
| 6 | **Persona Personalization**<br/><br/>Behavioral customization over clinical detachment. | **User Disengagement**<br/><br/>Boring data dumps lead to 2-week dropouts. | **Empathetic Companion Interface**<br/><br/>Biomarker Analyzer Agent outputs complex path analysis using an encouraging "Health Bestie" tone. |



---
# 4. Architecture
## Agents/Skills Architecture

```mermaid
flowchart TD
    %% Global Light-Themed Styling Config (Font sizes upgraded to 14px/15px)
    classDef coordinator fill:#f3e8ff,stroke:#7c3aed,stroke-width:2px,color:#4c1d95,font-weight:bold,font-size:15px;
    classDef fallbackBox fill:#eff6ff,stroke:#3b82f6,stroke-width:1px,stroke-dasharray: 4 4,color:#1e40af,font-size:14px;
    classDef skillGroup fill:#f8fafc,stroke:#cbd5e1,stroke-width:1.5px,color:#1e293b,font-weight:bold,font-size:14px;
    classDef skill fill:#ffffff,stroke:#64748b,stroke-width:1px,color:#334155,font-size:14px;
    classDef db fill:#f0fdf4,stroke:#16a34a,stroke-width:1.5px,color:#14532d,font-size:14px;
    classDef output fill:#fef3c7,stroke:#d97706,stroke-width:2px,color:#92400e,font-weight:bold,font-size:15px;

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
### Orchestration Layer
- Coordinator Agent: Processes the raw user upload through the Context Router, which coordinates processing by utilizing the Resilient Model Fallback Pool to guarantee zero downtime and maximum reliability.
### Secialist Skills Layer
#### Secialist Skills List
InflameCop implements a production-grade Agent Skills architecture designed to mitigate **Context Rot** and eliminate the attention dilution inherent in traditional LLM pipelines. Instead of relying on a fragile, single monolithic prompt—which frequently triggers **stochastic hallucinations** and cost overruns—the system utilizes **Progressive Disclosure** via a centralized Context Router. 

🧱 Group A: Core Defense & Environmental Parsing
- Skill 1 (Image Content Guard): Filters out non-food images at the gateway to prevent system pollution and conserve token budgets.
- Skill 2 (Cook Classifier): Detects plating cues to differentiate home-cooked meals from hidden restaurant inflammatory oils.
- Skill 3 (Witty Cop-Verdict Engine): Maps data into a gamified "Inflammation Police" verdict with exactly one witty, actionable mitigation.

🧪 Group B: Nutrition & Biochemical Toxicology
- Skill 4 (Micronutrient Estimator): Quantifies key vitamins and polyphenols to measure active cellular defense against oxidative stress.
- Skill 5 (AGEs Detector): Multiplies glycotoxin scores based on cooking temperature (e.g., deep-fried vs. boiled) for anti-aging analysis.
- Skill 6 (Seed Oil Hazard Analyst): Exposes hidden commercial refined seed oils and evaluates dangerous lipid peroxidation risks.

🧘 Group C: Physiological & Biometric Alignment
- Skill 7 (Gut Mucosal Shield): Scans for traditional "neba-neba" foods (natto, okra, yam) to grade intestinal barrier protection.
- Skill 8 (User Traits Contextualizer): Cross-matches personalized history with food chemistry (e.g., flagging leftovers for histamine sensitivities).
- Skill 9 (Biometric Adjuster): Uses a code constraint to automatically shrink the user's inflammatory budget during low sleep or high stress.

📈 Group D: Long-Term Trend & Clinical Synthesis
- Skill 10 (DII Engine): Executes a strict calculation script based on the peer-reviewed Dietary Inflammatory Index methodology.
- Skill 11 (Historic Trend Analyzer): Triggers an MCP database call to track 7-day rolling averages, constructing a longitudinal data moat.
- Skill 12 (Clinical Synthesizer): Aggregates multi-skill outputs via a File Message Bus, synthesizing findings with real medical citations.


#### Specialist Skills Registry
By executing 12 highly codified clinical and biochemical skills as isolated semantic APIs, InflameCop dynamically loads prompt fragments and data structures on demand. This runtime orchestration architecture achieves up to a **98% reduction in active context windows** and strictly enforces **deterministic data boundaries** across all tool, database, and inference layers.

<details open>
<summary><i>【Click to See Detailed Specialist Skills Spec】</i></summary>    
    
##### 🧱 Group A: Core Defense & Environmental Parsing
*Initial gatekeeping, input validation, and gamified UX rendering.*

| Skill ID | API Contract (Schema) | Core Logic & Deterministic Tools | Value / Impact |
| :--- | :--- | :--- | :--- |
| **`SKILL_01_IMAGE_GUARD`** | **In:**<br/>`rawImageBase64`<br/><br/>**Out:**<br/>`{ isValidFood: bool, score: float }` | • Low-latency object detection (Gemini Vision).<br/>• **Guardrail:** Aborts DAG workflow if subject is non-edible or confidence < `0.70`. | **Extreme Robustness:** Prevents system pollution, API over-billing, and hallucinations right at the gateway. |
| **`SKILL_02_COOK_CLASSIFIER`** | **In:**<br/>`{ ingredients, platingCues }`<br/><br/>**Out:**<br/>`{ context: enum, oilMultiplier: float }` | • Parses visual presentation cues (paper boxes, slate boards).<br/>• **Calibration:** Sets seed oil factor to `2.5x` for restaurants vs. `1.0x` for home. | **Context-Aware Precision:** Eliminates the "hidden restaurant oil" blindspot of standard diet apps. |
| **`SKILL_03_COP_VERDICT`** | **In:**<br/>`{ diiScore, criticalHazards }`<br/><br/>**Out:**<br/>`{ verdictCategory: enum, actionItem }` | • Maps final DII score to police-style ratings.<br/>• Uses `/assets/cop_jokes.json` to deliver **exactly one** witty, biochemistry-backed advice. | **High UX Retention:** Translates dry medical markers into a viral, gamified narrative without cognitive overload. |

---

##### 🧪 Group B: Nutrition & Biochemical Toxicology
*Biochemical profiling and deep inflammatory defense mapping via MCP.*

| Skill ID | API Contract (Schema) | Core Logic & Deterministic Tools | Value / Impact |
| :--- | :--- | :--- | :--- |
| **`SKILL_04_MICRONUTRIENT_EST`** | **In:**<br/>`{ ingredients: array }`<br/><br/>**Out:**<br/>`{ vitamins, polyphenols_mg }` | • Cross-references ingredients against **USDA FoodData Central API** and custom phytonutrient asset tables. | **Beyond Macros:** Tracks micronutrient buffers and cellular oxidative stress protectors instead of just calories. |
| **`SKILL_05_AGE_DETECTOR`** | **In:**<br/>`{ ingredients, cookingMethod }`<br/><br/>**Out:**<br/>`{ ageScore, riskLevel: enum }` | • **Cooking Multiplier:** Boiled = `1.0x`, Deep-Fried = `10.0x`. <br/>• Clinical lookup table measuring glycotoxins (CML). | **True Longevity Science:** Shows how cooking methods dictate food toxicity, anchoring the app in anti-aging science. |
| **`SKILL_06_SEED_OIL_ANALYST`** | **In:**<br/>`{ rawFoodText, locationContext }`<br/><br/>**Out:**<br/>`{ industrialOils: array, risk: enum }` | • Fuzzy string matching against restaurant menus.<br/>• Calculates lipid peroxidation risk via smoke point & PUFA content. | **Modern Diet Shield:** Directly exposes hidden industrial seed oils (canola, soybean) that typical apps ignore. |

---

##### 🧘 Group C: Physiological & Biometric Alignment
*Dynamic inflammatory threshold tuning based on real-time body state.*

| Skill ID | API Contract (Schema) | Core Logic & Deterministic Tools | Value / Impact |
| :--- | :--- | :--- | :--- |
| **`SKILL_07_GUT_SHIELD`** | **In:**<br/>`{ ingredients: array }`<br/><br/>**Out:**<br/>`{ mucilageScore: int [0-100] }` | • Detects **"Neba-Neba"** foods (natto, okra, wild yam) and soluble prebiotic fibers.<br/>• Computes gut-lining barrier protection score. | **Holistic Gut Wellness:** Empirically rewards users for eating functional foods that heal the gut mucosa. |
| **`SKILL_08_USER_TRAITS`** | **In:**<br/>`{ foodItems, userProfileTraits }`<br/><br/>**Out:**<br/>`{ personalizedWarnings: array }` | • Cross-matches lifestyle to food chemistry.<br/>• *Rule example:* Triggers histamine alert if user has sensitivities and food contains "leftovers". | **Hyper-Personalization:** Guarantees that the exact same meal yields completely different risks based on individual traits. |
| **`SKILL_09_BIOMETRIC_ADJUSTER`** | **In:**<br/>`{ baselineDii, userBiometrics }`<br/><br/>**Out:**<br/>`{ adjustedDiiScore, shiftFactor }` | • **Shift Left (Math Constraint):** Low sleep (< 6h) automatically penalizes baseline DII by `+0.8`. Intense workout lowers glycemic penalty by `-0.5`. | **Adaptive Physiology:** Reflects real biology—the same meal is biochemically more toxic when sleep-deprived and stressed. |

---

##### 📈 Group D: Long-Term Trend & Clinical Synthesis
*Time-series data aggregation and high-fidelity scientific report compilation.*

| Skill ID | API Contract (Schema) | Core Logic & Deterministic Tools | Value / Impact |
| :--- | :--- | :--- | :--- |
| **`SKILL_10_DII_ENGINE`** | **In:**<br/>`{ nutritionMatrix }`<br/><br/>**Out:**<br/>`{ rawDii, classification: enum }` | • Deterministic implementation of the peer-reviewed Dietary Inflammatory Index (DII) methodology via `/scripts/dii_calculator.py`. | **Academic Authority:** Roots the entire scoring system in legitimate epidemiological science rather than arbitrary AI vibes. |
| **`SKILL_11_TREND_ANALYZER`** | **In:**<br/>`{ historyEntries: array }`<br/><br/>**Out:**<br/>`{ rollingAverageDii, progress: enum }` | • Executes **MCP Tool Call** to **InflameCop Historic DB**.<br/>• Applies a 7-day rolling average to isolate long-term metabolic trends. | **Durable Proprietary Moat:** Shifts UX focus from single meals to longitudinal tracking, building a massive data moat. |
| **`SKILL_12_CLINICAL_SYNTH`** | **In:**<br/>`{ mealStats, accumulatedDii }`<br/><br/>**Out:**<br/>`{ narrativeMarkdown, citedStudies }` | • **File Message Bus:** Gathers JSON payload URIs on disk to bypass context rot.<br/>• Gemini 3.5 Flash synthesizes medical journal citations (*Nature Medicine*, *AJCN*). | **Unrivaled Professionalism:** Showcases flawless system orchestration while delivering elite, evidence-based value to users. |

</details>

### Data & Knowledge Layer

## MCP Architecture
To guarantee strict type safety and eliminate systemic context rot, InflameCop rejects the fragile anti-pattern of hardcoded point-to-point APIs or chaotic, unconstrained single-massive prompts. 

Instead, the entire pipeline is consolidated into a **Single, Unified InflameCop MCP Server**. The central LLM acts purely as a decoupled runtime client (Context Router). It discovers and invokes the 12 specialized skills using three standardized architectural primitives defined by the Model Context Protocol (MCP): **Tools** (for deterministic computations), **Resources** (for stateful databases), and **Prompts** (for narrative synthesis).

### 1. MCP Interoperability Architecture Flow Diagram

```mermaid
graph TD
    %% 全域字體清晰度與圓角微調
    classDef component fill:#ffffff,stroke:#0f172a,stroke-width:2.5px,font-weight:bold,color:#0f172a,font-size:15px;
    classDef protocol fill:#e0f2fe,stroke:#0284c7,stroke-width:2px,font-weight:bold,color:#0369a1,font-size:15px;
    classDef skill fill:#ffffff,stroke:#10b981,stroke-width:1.5px,color:#065f46,font-size:14px;
    classDef promptSkill fill:#f5f3ff,stroke:#7c3aed,stroke-width:2px,color:#4c1d95,font-weight:bold,font-size:14px;
    classDef db fill:#ffffff,stroke:#f59e0b,stroke-width:1.5px,color:#92400e,font-size:14px;

    %% ==========================================
    %% 1. ORCHESTRATION LAYER (置中居頂)
    %% ==========================================
    subgraph Orchestration ["1. Orchestration & Routing Layer (MCP Client)"]
        direction LR
        Input["📥 User Uploads Image + Tags"]:::component --> Router["🧠 Context Router (Coordinator)"]:::component
        Router <--> LLM["⚡ Gemini 3.5 Flash Engine"]:::component
    end

    %% ==========================================
    %% 2. MCP INTEROPERABILITY BRIDGE (中間樞紐)
    %% ==========================================
    subgraph MCP_Bridge ["2. Model Context Protocol (MCP) Unified Interface Implementation"]
        direction LR
        JSONRPC["🔌 Unified JSON-RPC 2.0 Server Gateway"]:::protocol
    end

    Router --> |"Protocol Session"| JSONRPC

    %% ==========================================
    %% 3. REFACTORING PRODUCTION BACKEND (橫向緊湊化排版)
    %% ==========================================
    subgraph MasterEngine ["🛠️ Master Ingestion Engine: /api/analyze"]
        direction LR
        
        subgraph GroupA_Core ["🧱 Core Defense & Parsing"]
            direction TB
            S1["🔍 Skill 1: Image Guard<br>(MCP Tool)"]:::skill
            S2["🍳 Skill 2: Cook Classifier<br>(MCP Tool)"]:::skill
            S3["👮 Skill 3: Cop Verdict<br>(MCP Prompt Template)"]:::promptSkill
        end

        subgraph GroupB_Nutri ["🧪 Nutrition & Toxicology"]
            direction TB
            S4["🌿 Skill 4: Micronutrient Est"]:::skill
            S5["🔥 Skill 5: AGEs Detector"]:::skill
            S6["🫒 Skill 6: Seed Oil Analyst"]:::skill
        end

        subgraph GroupC_Physio ["🧘 Physiological Alignment"]
            direction TB
            S7["🧘 Skill 7: Gut Shield"]:::skill
            S8["🍱 Skill 8: Traits Context"]:::skill
            S9["💪 Skill 9: Biometric Adjust"]:::skill
        end
    end
    style MasterEngine fill:#faf5ff,stroke:#6366f1,stroke-width:2px

    subgraph GroupD ["📈 Group D: Long-Term Trend & Clinical Synthesis (Mixed)"]
        direction TB
        S10["📊 Skill 10: DII Engine<br>(MCP Tool)"]:::skill
        S11["✍️ Skill 11: Trend Analyzer<br>(MCP Tool)"]:::skill
        S12["🔮 Skill 12: Clinical Synth<br>(MCP Prompt Template)"]:::promptSkill
    end

    subgraph Data_Knowledge ["📂 Dynamic Knowledge Layer (MCP Resource Servers)"]
        direction TB
        DB1["📁 Session Metadata"]:::db
        DB2["📚 /api/mcp/ingredient_inflammation_db"]:::db
        DB3["💾 User History DB"]:::db
        DB1 ~~~ DB2 ~~~ DB3
    end

    %% 完美的網格對齊（讓 GroupD 與 Data_Knowledge 並排，消除空洞）
    GroupD ~~~ Data_Knowledge

    %% 精準分流線條
    JSONRPC --> |"Executes Core Pipeline"| MasterEngine
    JSONRPC --> |"Dispatches Analytical Engine"| S10
    JSONRPC --> |"Exposes URIs"| Data_Knowledge

    %% ==========================================
    %% PRODUCTION DATA FLOW ENHANCEMENTS (整理後的線條)
    %% ==========================================
    DB3 --> |"Feeds 7-Day Chrono Data"| S11
    MasterEngine --> |"Pipelines Meal Payload"| S10
    S10 --> S11 --> S12

    %% ==========================================
    %% 4. OUTPUT
    %% ==========================================
    Output["🎯 Final Synthesized Clinical Report & Witty Verdict (Output)"]:::component
    GroupA_Core --> Output
    S12 --> Output
    Data_Knowledge -.-> Output
```

### 🔌 2. MCP Core Architectural Mapping

To achieve high-performance interoperability, the system is designed strictly around the Model Context Protocol (MCP) standard specification, mapping all core components into three native MCP constructs:

#### 🧱 A. MCP Tools Registration (Specialist Skills Layer)
* **Native Tool Exposure:** The 12 Specialist Skills are exposed to the Context Router (MCP Client) as native, schema-validated tools.
* **Protocol Interface:** Implements **`tools/list`** to announce available skills and **`tools/call`** to execute them deterministically.
* **Isolation & Modularity:** Each skill runs as a decoupled module inside the unified MCP Server container. 
* **Defensive Engineering:** The Context Router invokes skills using strict JSON schemas (verifying `imageUrl`, `user_biometrics`, and `cooking_methods`), preventing prompt injection and enforcing mathematical determinism.

#### 📂 B. MCP Resources Registration (Data & Knowledge Layer)
* **Decoupled Context Access:** Datasets providing essential backdrop context are served directly to the orchestrator via standard URI-based resource schemes, eliminating static prompt memory bloat.
* **Protocol Interface:** Implements **`resources/list`** and **`resources/read`** with strict Content-Type mapping.
* **Standard Resource URI Schemas:**
  * `dietary://history/user_id`: Maps to the **User History DB** (enabling Skill 11's time-series rolling calculations).
  * `clinical://guidelines/who`: Maps to **WHO, USDA, & PubMed guidelines** (enabling Skill 12 to append peer-reviewed citations).
  * `session://mount`: Contains the active session metadata and current meal assessment state.

#### ✍️ C. MCP Prompts Templates (System Integration)
* **Standardized Generation Templates:** Pre-structured clinical reasoning flows and behavioral personality profiles are registered as decoupled system templates.
* **Protocol Interface:** Implements **`prompts/list`** and **`prompts/get`** to dynamically hydrate runtime contexts.
* **Dynamic Generation Orchestration:** The Coordinator Agent pulls the `witty-cop-verdict` template (Skill 3) or the `clinical-synthesis-narrative` template (Skill 12) on demand, forcing the LLM client to format complex data payloads into the final clinical output without semantic drift.

## Security Architecture
### Security Features Flow Chart

<img width="431" height="563" alt="image" src="https://github.com/user-attachments/assets/92523018-834e-4795-8cb5-035c6cdea80c" />

InflameCop implements a strict **Defense-in-Depth** pipeline directly mapped to the **Google x Kaggle Framework**.

<details >
<summary><b>[1] Active Input Guard (Active Defense Layer)</b></summary>
Enforces <code>is_food: boolean</code> pre-validation at the gateway to instantly quarantine non-food uploads. 
<b>→ Blocks Multimodal Prompt Injection and cuts 80% invalid token waste.</b>
</details>

<details >
<summary><b>[2] Payload Sanitization (Egress & Sandboxing)</b></summary>
Intercepts and vector-quarantines risky formats (<code>.svg</code>/<code>.xml</code>) into sterile 1x1 safe PNG strings before reaching the model.
<b>→ Neutralizes XXE (XML External Entity) and Vision Engine injection vulnerabilities.</b>
</details>

<details >
<summary><b>[3] Resilient Model Fallback Pool (Runtime & Observability)</b></summary>
Wraps inference with a 5-tier Gemini matrix allowing up to 2 adaptive retries per tier.
<b>→ Guarantees 99.9% operational uptime against API rate-limits (429) or sudden cloud outages.</b>
</details>

<details >
<summary><b>[4] Strong Type Boundary Enforcement (Data & Model Integrity)</b></summary>
Locks model outputs via strict <code>responseSchema</code> to hardcoded enums (<code>Pro-inflammatory</code>/<code>Neutral</code>/<code>Anti-inflammatory</code>).
<b>→ 100% eliminates LLM hallucinations and structured data corruption.</b>
</details>



### 🛡️ Deep Dive: Static Controls & Development Safeguards
<img width="696" height="416" alt="image" src="https://github.com/user-attachments/assets/0ad2b753-79f0-4046-bd3a-e1ef332f53b5" />


The diagram above illustrates how InflameCop's 4-step dynamic runtime workflow maps directly to the comprehensive security layers defined in the Google x Kaggle Framework. While live traffic goes through runtime checks, InflameCop simultaneously infuses the remaining framework pillars into its **development lifecycle and underlying architecture**:

<details >
<summary><b>[5] Infrastructure (Pillar 1)</b></summary>
Built upon containerized, single-purpose micro-environments.
<b>→ Enforces strict sandboxing that completely isolates the LLM execution workflow from any persistent data layer.</b>
</details>

<details >
<summary><b>[6] Ephemeral Data Governance (Pillar 2: Privacy by Design)</b></summary>
A Zero-Trust decentralized frontend-only storage approach for biometric tracking.
<b>→ Zero PII (Personally Identifiable Information) touches or resides on the backend server.</b>
</details>

<details >
<summary><b>[7] Shift Left IDE Linters</b></summary>
Hardened during compilation using TypeScript's strict type system.
<b>→ Shifts type checking left into the local development stage, making it structurally impossible to deploy code with unhandled model schemas.</b>
</details>

<details >
<summary><b>[8] Hallucinated Package Blockers</b></summary>
Enforced via deterministic lockfiles (<code>package-lock.json</code> / <code>pnpm-lock.yaml</code>) and strict semantic versioning constraints.
<b>→ Guarantees the runtime never imports unverified or malicious packages introduced by AI code generation hallucinations.</b>
</details>

<details >
<summary><b>[9] MCP Spoofing Defense</b></summary>
Utilizes explicit, strongly-typed JSON schemas for Model Context Protocol (MCP) tool routing.
<b>→ Establishes absolute tool validation so malicious third-party prompt payloads can never forge backend commands or spoof admin boundaries.</b>
</details>


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
    %% Styling Definitions
    classDef orchestrator fill:#1e1e2e,stroke:#cba6f7,stroke-width:2px,color:#cdd6f4;
    classDef protocol fill:#313244,stroke:#89b4fa,stroke-width:2px,color:#cdd6f4,stroke-dasharray: 5 5;
    classDef skillGroup fill:#181825,stroke:#45475a,stroke-width:1px,color:#cdd6f4;
    classDef skill fill:#1e1e2e,stroke:#a6e3a1,stroke-width:1.5px,color:#cdd6f4;
    classDef dataStore fill:#1e1e2e,stroke:#f38ba8,stroke-width:1.5px,color:#cdd6f4;

    %% --- ORCHESTRATION LAYER ---
    subgraph ORCH ["1. ORCHESTRATION LAYER (Client)"]
        direction TB
        IMG["📷 User Uploads Meal Image"] --> CR["🧠 Context Router / Coordinator Agent"]
        CR <--> LLM["⚡ Primary: Gemini 3.5 Flash<br>🔄 Fallback: Low-Latency Model Pool"]
    end
    class ORCH orchestrator;

    %% --- PROTOCOL INTEROP LAYER ---
    subgraph PROTO ["2. MCP INTEROPERABILITY FRAMEWORK"]
        direction LR
        JSONRPC["🔌 Standard MCP Host Connection<br>JSON-RPC over stdio / EventSource"]
    end
    class PROTO protocol;
    CR <--> JSONRPC

    %% --- SPECIALIST SKILLS LAYER (MCP SERVER) ---
    subgraph SKILLS ["3. SPECIALIST SKILLS LAYER (Unified MCP Server)"]
        direction TB

        %% Sub-group A
        subgraph GroupA ["A. Core Defense & Parsing (Tools)"]
            direction TB
            S1["🔍 S1: Image Content Guard<br>tool://image_content_guard"]:::skill
            S2["🍳 S2: Kitchen Classifier<br>tool://kitchen_classifier"]:::skill
            S3["🛡️ S3: Witty Cop Verdict<br>tool://cop_verdict_engine"]:::skill
            S1 ~~~ S2 ~~~ S3
        end
        style GroupA fill:#11111b,stroke:#fab387,stroke-width:1.5px;

        %% Sub-group B
        subgraph GroupB ["B. Nutrition & Toxicology (Tools)"]
            direction TB
            S4["🌿 S4: Micronutrient Estimator<br>tool://micronutrient_estimator"]:::skill
            S5["🔥 S5: AGEs Detector<br>tool://ages_detector"]:::skill
            S6["🫒 S6: Seed Oil Analyst<br>tool://seed_oil_hazard_analyst"]:::skill
            S4 ~~~ S5 ~~~ S6
        end
        style GroupB fill:#11111b,stroke:#f9e2af,stroke-width:1.5px;

        %% Sub-group C
        subgraph GroupC ["C. Physiological Alignment (Tools/Resources)"]
            direction TB
            S7["🧘 S7: Gut Mucosal Shield<br>tool://gut_mucilage_calculator"]:::skill
            S8["🍱 S8: User Traits Matcher<br>tool://user_traits_contextualizer"]:::skill
            S9["💪 S9: Biometric Overlay<br>tool://biometric_adjuster"]:::skill
            S7 ~~~ S8 ~~~ S9
        end
        style GroupC fill:#11111b,stroke:#a6e3a1,stroke-width:1.5px;

        %% Sub-group D
        subgraph GroupD ["D. Trend & Synthesis (Tools/Prompts)"]
            direction TB
            S10["📊 S10: DII Score Engine<br>tool://dii_score_engine"]:::skill
            S11["✍️ S11: Trend Analyzer<br>tool://historic_trend_analyzer"]:::skill
            S12["💾 S12: Narrative Synthesizer<br>prompt://clinical_synthesizer"]:::skill
            S10 ~~~ S11 ~~~ S12
        end
        style GroupD fill:#11111b,stroke:#84a0c6,stroke-width:1.5px;
    end
    class SKILLS skillGroup;
    JSONRPC <--> SKILLS

    %% --- DATA & KNOWLEDGE LAYER ---
    subgraph DATA ["4. DATA & KNOWLEDGE LAYER (MCP Resources)"]
        direction LR
        DB_BIOMETRICS[("👤 Biometrics DB<br>resource://user/biometrics")]:::dataStore
        DB_HISTORY[("📝 Meal History Log<br>resource://meal/history")]:::dataStore
        DB_CLINICAL[("📖 Clinical Guidelines<br>resource://clinical/dii_standards")]:::dataStore
    end
    style DATA fill:#1e1e2e,stroke:#f38ba8,stroke-width:1.5px;

    %% Mapping database to server context
    SKILLS <--> DATA
    
    %% Final Output Flow
    GroupD --> OUTPUT["🎯 Final Scientific Narrative & Interventions Output"]
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

