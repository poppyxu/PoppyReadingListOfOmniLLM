# Simplex Omni Models — Research Index

_Last updated: 2026-10-09 · [Back to README](../README.md#simplex-omni-models)_

## Scope and terminology

In this repository, "Simplex" is the historical name for **offline / turn-based omni-modal model evaluation**, not necessarily one-way simplex in the communications-engineering sense (alternating dialogue is closer to half-duplex). Streaming speech output alone does **not** make an interaction full-duplex.

For each model, distinguish: **input modalities**, **output modalities**, **technical report vs product announcement**, **realtime API variants vs model generations**, and **model-native vs orchestrator-supported agent capabilities**.

## 1. Qwen Omni model family

| Model | Year | Key mechanisms worth studying | Paper / code |
| --- | --- | --- | --- |
| **Qwen2.5-Omni** | 2025 | Thinker–Talker decomposition; TMRoPE multimodal temporal alignment; block-wise input and streaming speech. | [Paper](https://arxiv.org/abs/2503.20215) · [GitHub](https://github.com/QwenLM/Qwen2.5-Omni) |
| **Qwen3-Omni** | 2025 | MoE Thinker–Talker, Audio Transformer, multi-codebook audio prediction; Instruct / Thinking / Captioner branches. | [Paper](https://arxiv.org/abs/2509.17765) · [GitHub](https://github.com/QwenLM/Qwen3-Omni) |
| **Qwen3.5-Omni** | 2026 | Hybrid-Attention MoE; 256K context; ARIA alignment of text and speech; long audio-video understanding and generation. | [Paper](https://arxiv.org/abs/2604.15804) |
| **Qwen3.8-Omni-Flash** | 2026 | Native multimodal co-training, sparse MoE, 1M context, agentic long-horizon video/audio workflows, Qwen-MM-Plugins and Qwen-Live-Harness. | [Paper](https://arxiv.org/abs/2609.25611) |

**Related named variants (not four more independent technical papers):** Qwen3-Omni-Instruct / Thinking / Captioner; Qwen3-Omni-Flash; Qwen3.5-Omni-Plus / Flash; Qwen3.8-Omni-Flash-Realtime. Treat realtime endpoints as **Duplex / Streaming cross-references**, not proof that offline and realtime models have identical capabilities.

**Earlier foundations:** [Qwen2-Audio](https://arxiv.org/abs/2407.10759) (audio-language), [Qwen2.5-VL](https://arxiv.org/abs/2502.13923) (vision-language) and general Qwen reasoning models belong under **Foundations**, rather than counting as complete omni systems.

### Research questions for Qwen

- How are perception and speech synthesis separated or shared across the Thinker and Talker?
- What do TMRoPE, streaming token alignment and ARIA change about long audio-video understanding and synchronized output?
- Which improvements reflect *native model training* versus improvements from tools, subagents and harness orchestration?
- How should an offline Qwen variant be compared to its realtime endpoint without conflating latency and intelligence?

## 2. Xiaomi MiMo model family

| Model | Date | What to track | Evidence |
| --- | --- | --- | --- |
| **MiMo-V2-Omni** | 2026-03 | Integrated image, video and audio perception; structured tool calls, UI grounding, perception-to-action reasoning. | [Official introduction](https://mimo.xiaomi.com/mimo-v2-omni) |
| **MiMo-V2.5** | 2026-04 | Native text/image/video/audio input, **text output**, 1M context, tool-use and long-horizon multimodal agents. | [Official model specs](https://mimo.mi.com/models/en-US/mimo-v2.5) |
| **MiMo-V2.6-Pro** | 2026-09 | Native fully multimodal flagship; scaling agent-focused reinforcement learning and long-horizon tasks. | [Official release](https://mimo.mi.com/docs/en-US/news/latest/v2-6) |
| **MiMo-V2.6-Flash** | 2026-09 | Native fully multimodal efficient companion; capability-cost trade-off. | [Official release](https://mimo.mi.com/docs/en-US/news/latest/v2-6) |

**Related series, tracked separately:** [MiMo-VL](https://arxiv.org/abs/2506.03569) and [MiMo-Audio](https://arxiv.org/abs/2512.23808) are specialized *vision-language* and *audio-language* foundations. MiMo-V2.5-Pro is a separate high-capability reasoning/agent model; do not automatically ascribe all MiMo-V2.5 base-model multimodal I/O specifications to Pro without confirming its model-specific interface. MiMo-V2.6-Pro-UltraSpeed is a latency-optimized service variant, not another research generation.

**Evidence note:** The first V2 Omni product and the V2.5 version are documented on official product pages. V2.6 has an official release announcement and open weights/report links there. Mark sources as **paper / technical report / release / API docs** rather than representing every model as having an independently published arXiv paper.

### Research questions for MiMo

- How does multimodal pretraining support **perception → reasoning → tool action**?
- How does it differ from systems that natively **generate speech**?
- Which improvements come from reward design, long-horizon agent environments and scaled RL?
- How should tool-use task success be separated from perceptual evaluation?

## 3. Other well-known omni families

| Family | Important generation(s) | Why it matters | Primary links |
| --- | --- | --- | --- |
| **Baichuan-Omni** | 2024 → 1.5 (2025) | Two-stage multimodal alignment, staged training, audio tokenizer and audio output. | [2024](https://arxiv.org/abs/2410.08565) · [1.5](https://arxiv.org/abs/2501.15368) |
| **VITA** | 2024 → VITA-1.5 (2025) | Early open interactive omni architecture; vision/speech progressive training. | [VITA](https://arxiv.org/abs/2408.05211) · [1.5](https://arxiv.org/abs/2501.01957) |
| **Ola** | Ola (2025) | Progressive alignment of image/video/audio with video bridging modalities. | [Paper](https://arxiv.org/abs/2502.04328) · [GitHub](https://github.com/Ola-Omni/Ola) |
| **MiniCPM-o** | MiniCPM-o 2.6 (2025) | Compact on-device multimodal perception and streaming speech. | [Model](https://huggingface.co/openbmb/MiniCPM-o-2_6) · [GitHub](https://github.com/OpenBMB/MiniCPM-o) |
| **OmniVinci** | OmniVinci (2025) | OmniAlignNet, Temporal Embedding Grouping and cross-modal temporal binding. | [Paper](https://arxiv.org/abs/2510.15870) · [Project](https://nvlabs.github.io/OmniVinci/) |
| **NVIDIA Nemotron Omni** | Nemotron 3 Nano Omni (2026) | Efficient open vision/audio/video/text model built on a sparse MoE backbone. | [Paper](https://arxiv.org/abs/2604.24954) |

**Adjacent, not equivalent:**
- [VideoChat](https://arxiv.org/abs/2305.06355) and [VideoChat3](https://arxiv.org/abs/2607.14935): primarily **video-language**; useful for video understanding and temporal alignment, not necessarily full audio/video omni I/O.
- [MiniCPM-o 4.5](https://arxiv.org/abs/2604.27393): native realtime full-duplex interaction; place primarily in [Duplex Omni Models](duplex-omni-models.md).
- GPT-4o and Gemini Native Audio: useful **closed-system reference points** for architecture / capability discussions, but source transparency is different from open technical reports.

## 4. Comparison template for each paper

| Axis | Questions |
| --- | --- |
| Input / output | Text, image, audio, video **in**; text/audio/video **out**? |
| Perception & fusion | Separate encoders or shared representation? Late fusion, alignment, or native co-training? |
| Temporal modeling | Temporal position embedding, token rate, alignment, video sampling, streaming constraints? |
| Speech output | Speech codec, semantic/acoustic tokens, diffusion, latency and sync quality? |
| Data pipeline | Pretraining mixture, video/audio alignment, synthetic/real conversation and data quality? |
| Post-training | SFT, preference optimization, RL environments, reward, agent trajectories? |
| Agent capability | Tool calls, GUI grounding, action execution, long-horizon task completion? |
| Evaluation | Which baselines, modality-specific performance, long-context and agent benchmarks? |
| Evidence | Public report, official model page, code, weights, API-only claim? |

## 5. Suggested reading paths

**Perception + speech generation:** Qwen2.5-Omni → Qwen3-Omni → Qwen3.5-Omni; compare Baichuan-Omni-1.5 and MiniCPM-o 2.6.

**Joint omni understanding:** VITA → Ola → OmniVinci → Nemotron 3 Nano Omni.

**Agentic omni modeling:** MiMo-V2-Omni → MiMo-V2.5 → MiMo-V2.6; compare Qwen3.8-Omni-Flash.

**Duplex & real-time:** Use [Duplex Omni Models](duplex-omni-models.md) and do not infer duplex solely from streaming output.
