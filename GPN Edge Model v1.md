# GPN Edge Model v1.0  
## Data Structure Specification for Glyph Problem Network

**Status:** Frozen  
**Version:** 1.0  
**Applies to:** GPN Specification v1.0  
**Related Protocol:** GLYPH Core Protocol v1.0  

---

## 1. Purpose

This document defines the **canonical data model for edges** in the Glyph Problem Network (GPN).

It specifies:
- How relationships between GLYPHs are represented as data
- Mandatory and optional fields
- Validation rules
- Constraints for consistency and integrity

This document does **not** define visualization, algorithms, scoring, or analytics.

---

## 2. Edge Concept

An **Edge** represents a **single, explicit relationship** between two GLYPHs.

Edges do not represent:
- Solutions
- Actions
- Decisions
- Ownership
- Responsibility

Edges represent **problem-level structural relationships only**.

---

## 3. Edge Identity

Each edge must have a unique identifier.

### 3.1 Edge ID Format

EDGE-[SEQUENTIAL NUMBER]


**Examples:**


EDGE-001
EDGE-014
EDGE-128


**Rules:**
- Sequential numbering
- IDs are immutable
- IDs carry no priority or weight

---

## 4. Core Edge Structure

Every edge MUST contain the following fields:

| Field | Required | Description |
|------|---------|-------------|
| Edge_ID | Yes | Unique identifier |
| Source_GLYPH_ID | Yes | Origin GLYPH |
| Target_GLYPH_ID | Yes | Destination GLYPH |
| Relationship_Type | Yes | Type of relationship |
| Direction | Yes | Directionality |
| Justification | Yes | Structural rationale |
| Validation_Status | Yes | Validation state |
| Version | Yes | Edge version |
| Created_Date | Yes | Creation date |
| Validator | Yes | Validator identity |

---

## 5. Field Specifications

### 5.1 Edge_ID

**Definition:** Unique identifier of the edge.

**Format:**  


EDGE-###


**Validation Rules:**
- Must be unique
- Cannot be reused
- Cannot change once assigned

---

### 5.2 Source_GLYPH_ID

**Definition:** The GLYPH from which the relationship originates.

**Format:**  


GLYPH-[SYSTEM]-[###]


**Rules:**
- Must exist in the GLYPH dataset
- Must be validated or active

---

### 5.3 Target_GLYPH_ID

**Definition:** The GLYPH to which the relationship points.

**Rules:**
- Must exist
- Cannot equal Source_GLYPH_ID

---

### 5.4 Relationship_Type

**Definition:** Semantic classification of the relationship.

**Allowed Values (v1.0):**
- SHARED_VARIABLE
- SHARED_IMPACT
- CAUSAL_DEPENDENCY
- STRUCTURAL_SIMILARITY
- TEMPORAL_RECURRENCE

**Rules:**
- Exactly one value per edge
- Multi-type relationships require multiple edges

---

### 5.5 Direction

**Definition:** Directionality of the relationship.

**Allowed Values:**
- UNIDIRECTIONAL
- BIDIRECTIONAL

**Rules:**
- Causal relationships MUST be UNIDIRECTIONAL
- Shared relationships MAY be BIDIRECTIONAL

---

### 5.6 Justification

**Definition:** Structured explanation of why the relationship exists.

**Requirements:**
- Must reference fields inside the GLYPHs (Variables, Impact, Causal Chain)
- Must be factual and observable
- Must NOT contain solutions or opinions

**Example:**


Both GLYPHs reference "lack of standardization" as a structural variable affecting process efficiency.


---

### 5.7 Validation_Status

**Allowed Values:**
- DRAFT
- UNDER_REVIEW
- VALIDATED
- REJECTED
- DEPRECATED

**Rules:**
- Only VALIDATED edges may be used for analysis
- Rejected edges remain documented

---

### 5.8 Version

**Format:**


MAJOR.MINOR


**Rules:**
- Increment MINOR for clarification
- Increment MAJOR if relationship meaning changes

---

### 5.9 Created_Date

**Format:**  
ISO 8601 (YYYY-MM-DD)

---

### 5.10 Validator

**Definition:** Human responsible for validation.

**Format:**
- Name
- Role (Peer / Expert / Protocol)

---

## 6. Optional Fields

| Field | Description |
|------|-------------|
| Confidence_Level | Qualitative (Low / Medium / High) |
| Evidence_Reference | Dataset, document or observation |
| Notes | Clarifications |

Optional fields do not affect validity.

---

## 7. Edge Validation Rules

An edge is VALID only if:

- Both GLYPHs exist and are valid
- Relationship_Type is allowed
- Direction complies with relationship type
- Justification is coherent and non-solutional
- Validator is defined

---

## 8. Prohibited Edge Content

Edges MUST NOT:
- Contain recommendations
- Propose interventions
- Assign accountability
- Rank problems
- Predict outcomes

---

## 9. Example Edge (Canonical)

```yaml
Edge_ID: EDGE-021
Source_GLYPH_ID: GLYPH-ORG-001
Target_GLYPH_ID: GLYPH-ORG-002
Relationship_Type: SHARED_VARIABLE
Direction: BIDIRECTIONAL
Justification: Both GLYPHs reference lack of process standardization affecting coordination and planning.
Validation_Status: VALIDATED
Version: 1.0
Created_Date: 2026-01-15
Validator: C. Falcão (Protocol)
