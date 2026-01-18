# GPN Feature Set v1.0  
## Mathematical and Technological Basis for Glyph Problem Network

**Status:** Frozen  
**Version:** 1.0  
**Related Documents:**  
- GLYPH Core Protocol v1.0  
- GPN Specification v1.0  
- GPN Edge Model v1.0  

---

## 1. Purpose

This document defines the **canonical feature set** for the Glyph Problem Network (GPN).

Its purpose is to:
- Translate GLYPHs and Edges into **structured features**
- Enable mathematical analysis, correlation, clustering and AI assistance
- Preserve the semantic integrity of the GLYPH Protocol

This document defines **what can be measured**, not **what must be decided**.

---

## 2. Conceptual Foundation

The GPN Feature Set treats:

- **GLYPHs as Nodes**
- **Edges as Relationships**
- **Fields as Feature Sources**

Each feature represents an **observable structural property** of a problem or its relationship to other problems.

---

## 3. Feature Categories

The feature set is organized into five canonical categories:

1. Node Structural Features  
2. Node Semantic Features  
3. Edge Relational Features  
4. Network Topological Features  
5. Temporal and Evolution Features  

Each category can be used independently or in combination.

---

## 4. Node Structural Features (GLYPH-Level)

Derived directly from the GLYPH canonical fields.

### 4.1 System Encoding

| Feature | Type | Description |
|------|------|-------------|
| system_org | Binary | Organizational system |
| system_ind | Binary | Industrial system |
| system_hum | Binary | Human system |
| system_env | Binary | Environmental system |
| system_dig | Binary | Digital system |

**Rule:** Exactly one system feature MUST be active per GLYPH.

---

### 4.2 Context Features

| Feature | Type | Description |
|------|------|-------------|
| context_frequency | Ordinal | Rare / Periodic / Frequent |
| context_scope | Ordinal | Local / Departmental / Organizational / Inter-organizational |
| context_stability | Ordinal | Stable / Volatile |

---

### 4.3 Symptom Features

| Feature | Type | Description |
|------|------|-------------|
| symptom_type | Categorical | Delay / Failure / Loss / Deviation |
| symptom_recurrence | Ordinal | Low / Medium / High |
| symptom_measurability | Binary | Observable & measurable |

---

### 4.4 Impact Features

| Feature | Type | Description |
|------|------|-------------|
| impact_time | Binary | Time affected |
| impact_cost | Binary | Cost affected |
| impact_quality | Binary | Quality affected |
| impact_risk | Binary | Risk increased |
| impact_sustainability | Binary | Environmental or social impact |

---

### 4.5 Variable Features

| Feature | Type | Description |
|------|------|-------------|
| variable_count | Integer | Number of variables |
| variable_structural | Binary | Structural variables present |
| variable_behavioral | Binary | Behavioral variables present |
| variable_technical | Binary | Technical variables present |
| variable_human | Binary | Human factors present |

---

## 5. Node Semantic Features

Derived from interpretation (human or assisted).

### 5.1 Causal Complexity

| Feature | Type | Description |
|------|------|-------------|
| causal_chain_length | Integer | Number of causal steps |
| feedback_loops | Binary | Presence of loops |
| causal_depth | Ordinal | Shallow / Moderate / Deep |

---

### 5.2 Leverage Characteristics

| Feature | Type | Description |
|------|------|-------------|
| leverage_type | Categorical | Structural / Informational / Behavioral |
| leverage_position | Ordinal | Early / Mid / Late in chain |

---

### 5.3 Success Definition Features

| Feature | Type | Description |
|------|------|-------------|
| success_metric_count | Integer | Number of criteria |
| success_quantified | Binary | Metrics are measurable |
| success_timebound | Binary | Time defined |

---

## 6. Edge Relational Features

Derived from GPN Edge Model.

### 6.1 Relationship Encoding

| Feature | Type |
|------|------|
| rel_shared_variable | Binary |
| rel_shared_impact | Binary |
| rel_causal_dependency | Binary |
| rel_structural_similarity | Binary |
| rel_temporal_recurrence | Binary |

---

### 6.2 Directionality

| Feature | Type |
|------|------|
| bidirectional | Binary |
| unidirectional | Binary |

---

### 6.3 Relationship Strength (Optional)

| Feature | Type | Description |
|------|------|-------------|
| confidence_level | Ordinal | Low / Medium / High |

---

## 7. Network Topological Features

Computed at graph level.

| Feature | Type | Description |
|------|------|-------------|
| node_degree | Integer | Number of connections |
| in_degree | Integer | Incoming edges |
| out_degree | Integer | Outgoing edges |
| betweenness | Float | Mediation potential |
| clustering_coefficient | Float | Local density |
| centrality | Float | Network importance |

---

## 8. Temporal and Evolution Features

| Feature | Type | Description |
|------|------|-------------|
| glyph_age | Integer | Days since creation |
| version_count | Integer | Number of revisions |
| edge_growth_rate | Float | New connections over time |
| recurrence_velocity | Ordinal | Speed of problem reappearance |

---

## 9. Analytical Applications Enabled

This feature set enables:

- Factor Analysis
- Clustering (unsupervised learning)
- Similarity search
- Pattern detection
- Probabilistic modeling
- Network analysis (SNA-inspired)
- AI-assisted problem formulation support

**None of these are mandatory.**

---

## 10. AI Usage Guidelines

AI systems may:
- Suggest feature extraction
- Identify clusters
- Detect anomalies
- Propose similarity links

AI systems MUST NOT:
- Define leverage points
- Rank problems by importance
- Replace human validation

---

## 11. Constraints and Safeguards

- Features must be traceable to GLYPH fields
- No feature may encode a solution
- Probabilities express uncertainty, not truth
- Mathematical abstraction must preserve semantic integrity

---

## 12. Final Statement

> The GPN Feature Set transforms structured problems into analyzable space — without turning problems into answers.

Meaning remains human. Structure becomes computable.

---

**END OF GPN FEATURE SET v1.0**
