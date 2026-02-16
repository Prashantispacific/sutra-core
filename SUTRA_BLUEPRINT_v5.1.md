# ⚔️ PROJECT SUTRA  
## The Sovereign Intelligence Kernel

> **Boring is Beautiful. Magic is Dangerous.**

---

| **Version** | **v5.1 (Codename: Iron-Lock)** |
|------------|--------------------------------|
| **Category** | Deterministic Inference Runtime |
| **Target** | Local-First Hardware (8–16 GB RAM) |
| **License** | Apache 2.0 |

---

## 🧠 Executive Summary

**SUTRA is not a model. It is a Kernel.**

While the AI industry oscillates between *Monolithic Giants* and *Agentic Swarms*,  
SUTRA introduces a third paradigm:

> **The Minimal Arbitration Layer (MAL)** — a deterministic, local-first inference kernel that treats intelligence as **modules**, not magic.

SUTRA enforces:
- Memory sovereignty  
- Deterministic routing  
- Explicit failure handling  

All on **consumer hardware**.

---

## ⚔️ Architectural Comparison

| Dimension | Monoliths | MoE | Agent Swarms | **SUTRA v5.1** |
|---------|-----------|-----|--------------|---------------|
| Architecture | Static | Hard-coded | Probabilistic | **Kernel + Modules** |
| Routing | None | Learned | Heuristic | **Deterministic** |
| Memory Cost | Very High | High | Unbounded | **~4 GB** |
| Reliability | Opaque | Debug-hard | Chaotic | **Predictable** |
| Sovereignty | Cloud | Partial | Partial | **Absolute** |

---

## 🏗️ System Architecture (ASCII)

```
User
 │
 ▼
Minimal Arbitration Layer (MAL)
 │ owns memory, routing, safety
 ▼
Logit-Lens Router
 │───────────────┐
 │               │
 ▼               ▼
Expert (LoRA)   Base Anchor Model
 │               │
 └───────┬───────┘
         ▼
       Output

Hybrid Memory (Kernel-Owned):
- Anchor Context: last 512 tokens
- LIV: 256-d Latent Intent Vector
```

---

## 🧩 Minimal Arbitration Layer (MAL)

The MAL acts as the **CPU scheduler of intelligence**.

**Responsibilities**
- Owns all memory
- Allocates VRAM
- Loads/unloads experts
- Handles failure recovery

**Constraints**
- No learned parameters
- No randomness
- No model-decided routing

**Rule**
> If an expert increases next-token entropy by >15% compared to the Base Anchor, it is evicted immediately.

---

## 🧠 Hybrid Memory Bus

| Tier | Component | Purpose |
|-----|----------|---------|
| 1 | Anchor Context (512 tokens) | Factual continuity |
| 2 | LIV (256-d vector) | Tone, style, intent |
| 3 | Paged KV Cache | Ephemeral expert state |

Memory is a **cache**, not identity.

---

## 🧭 Routing Engine (Logit-Lens v2)

Routing is based on **risk**, not capability.

**Signals**
- Entropy slope
- Mid vs output layer disagreement
- Atlas violations

Low confidence → fallback to Base Anchor.

---

## 📦 Expert Specification (.sutra)

Experts are **disposable cartridges**.

```yaml
metadata:
  name: "sutra-hindi-bard"
  version: "1.0.0"
  base_model_hash: "sha256:..."

atlas_config:
  affinity_heads: [layer_18, layer_19, layer_20]
  locked_layers: [layer_15, layer_22]

safety:
  refusal_profile: "strict"
  banned_tokens: ["json", "csv"]
```

Rules:
- Experts cannot self-route
- Experts cannot touch locked layers
- Over-answering experts are unsafe

---

## 🧪 Training Pipeline (SUTRA-SDK)

**Atlas Probe**
- Feed dataset to base model
- Record attention-head activation
- Generate affinity map

**Orthogonal Training**
```
L = L_task + λ · Similarity(W_lora, W_base_logic)
```

Goal: isolate specialist behavior without corrupting base reasoning.

---

## 🛡️ Failure-First Design

| Failure | Detection | Kernel Action |
|-------|-----------|---------------|
| IO Thrash | Load > 500 ms | Pause + prefetch |
| Semantic Drift | High entropy | Anchor reset |
| OOM | VRAM overflow | LRU eviction |
| Bad Expert | Atlas violation | Kernel panic |

All failures are logged and replayable.

---

## 🛠️ Implementation Roadmap

**Phase 1:** Kernel skeleton + llama.cpp  
**Phase 2:** Router + MAL arbitration  
**Phase 3:** SDK + expert packaging  
**Phase 4:** Documentation + expert hub  

---

## 📜 License & Ethos

**Apache 2.0**  
Architect: **Prashviz**

> Built for individuals, not platforms.  
> Infrastructure, not ideology.

---

### ✅ Status

SUTRA v5.1 is **production-grade kernel design**.  
Add benchmarks, not features.  
Add proofs, not promises.
