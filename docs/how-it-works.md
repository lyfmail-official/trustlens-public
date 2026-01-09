# How TrustLens Works

TrustLens uses a **multi-layered signal analysis pipeline** to assess risk indicators in text-based content.

The system is intentionally designed to avoid:
- Full content storage
- Behavioral profiling
- User identity tracking

---

## High-Level Architecture

User Input → Signal Extraction → Risk Aggregation → Explainable Output

Each step is modular, auditable, and replaceable.

---

## Step 1: Input Normalization

- Accepts raw text
- Removes excess formatting
- Validates content length and structure
- Rejects empty or invalid input

---

## Step 2: Content Classification

The system categorizes content into broad types such as:
- Health-related
- Financial claims
- Political messaging
- General informational content
- Viral or forwarded messages

This classification influences which signals are activated.

---

## Step 3: Claim Extraction

TrustLens attempts to identify:
- Declarative claims
- Promises or guarantees
- Cause–effect statements
- Time-bound assertions

This does **not** evaluate correctness — only *structure*.

---

## Step 4: Signal Analysis

Each signal operates independently and produces:
- A risk score
- A short explanation
- Optional supporting context

Signals are designed to be:
- Explainable
- Non-deterministic
- Resistant to manipulation

---

## Step 5: Aggregation

Signal results are combined using a weighted model that:
- Avoids dominance by a single signal
- Penalizes extreme certainty language
- Rewards neutral informational tone

---

## Step 6: User Output

The user sees:
- A confidence/risk percentage
- Human-readable explanations
- No hidden judgments
- No “true/false” labels

---

## Design Philosophy

TrustLens prioritizes:
- User understanding over automation
- Risk awareness over authority
- Transparency over black-box AI
