# Omni Intelligence

A curated list of papers on omni-modal intelligence: foundations, modeling and training, evaluation, and real-world agents.

Papers are listed in tables. The name links to the paper.

## Contents

- [Foundations](#foundations)
  - [LLM and Reasoning](#llm-and-reasoning)
  - [Vision-Language Models](#vision-language-models)
  - [Audio Foundations](#audio-foundations)
- [Omni Modeling and Training](#omni-modeling-and-training)
  - [Duplex Omni Models](#duplex-omni-models)
  - [Simplex Omni Models](#simplex-omni-models)
  - [Duplex Audio Models](#duplex-audio-models)
- [Omni Evaluation](#omni-evaluation)
  - [Simplex Omni Evaluation](#simplex-omni-evaluation)
  - [Duplex Omni Evaluation](#duplex-omni-evaluation)
  - [Audio Duplex Evaluation](#audio-duplex-evaluation)
- [Real-world Omni Agents](#real-world-omni-agents)
  - [Voice Agents](#voice-agents)
  - [Audio-Visual Agents](#audio-visual-agents)

## Foundations

Language, vision-language, and audio foundations that omni models build on.

### LLM and Reasoning

Language modeling, instruction following, long context, and multi-step reasoning used as the backbone for later omni systems.

### Vision-Language Models

How images and video connect to language: visual encoders, connectors into the LLM, joint training, and instruction tuning.

### Audio Foundations

Speech and general audio before fusion with other modalities: recognition, speaker and paralinguistic cues, representation, and speech generation.

## Omni Modeling and Training

How text, vision, and audio are combined in one model and trained for interaction over time.

### Duplex Omni Models

The model watches a live stream and can decide to speak, stay silent, or keep going while new frames arrive.

| Model | Venue | What it does | Links |
| --- | --- | --- | --- |
| [Realtime-Venus](https://arxiv.org/abs/2609.13814) | Venus Team, arXiv 2026 | Full-duplex system with two models. Realtime-Venus-Omni does audio-visual dialogue. A background harness can reason and use tools while the conversation continues. | |
| [MOSS-VL](https://arxiv.org/abs/2608.15045) | Wang et al., arXiv 2026 | Real-time vision-language interaction. The Realtime variant keeps seeing new frames while it generates, and is trained on when to speak, stay silent, or revise. | [Project](https://openmoss.ai/MOSS-VL/moss-vl.html) |
| [JoyAI-VL-Interaction](https://arxiv.org/abs/2606.14777) | Yao et al., arXiv 2026 | Watches a live video and, each second, chooses to stay silent, respond, or hand the problem to a background model. | [Code](https://github.com/jd-opensource/JoyAI-VL-Interaction) |
| [DuplexOmni](https://arxiv.org/abs/2606.09186) | Huang et al., arXiv 2026 | Streaming audio and video in, text and speech out. An interaction layer speaks in real time, and a thinking layer handles reasoning and tools in parallel. | [Code](https://github.com/MuyeHuang/DuplexOmni) |
| [MiniCPM-o 4.5](https://arxiv.org/abs/2604.27393) | Cui et al., arXiv 2026 | Sees, listens, and speaks at the same time. Omni-Flow puts inputs and outputs on one timeline, including proactive reminders. | [Code](https://github.com/OpenBMB/MiniCPM-o) |
| [AURA](https://arxiv.org/abs/2604.04184) | Lu et al., arXiv 2026 | Streaming video model for real-time questions and proactive replies. It can remain silent or respond on its own. | [Project](https://aurateam2026.github.io/) |
| [Proact-VL](https://arxiv.org/abs/2603.03447) | Yan et al., ICML 2026 | A response head decides when to speak on a live video, aimed at commentary and guidance. | [Code](https://github.com/microsoft/AnthropomorphicIntelligence/tree/main/Proact-VL) |
| [Streamo](https://arxiv.org/abs/2512.21334) | Xia et al., CVPR 2026 | Streaming video assistant. Silence, standby, and response states decide when to speak. | [Code](https://github.com/maifoundations/Streamo) |
| [MMDuet2](https://arxiv.org/abs/2512.06810) | Wang et al., ICLR 2026 | During playback, decides from the video so far whether to reply or stay silent. Trained with multi-turn reinforcement learning. | [Code](https://github.com/yellow-binary-tree/MMDuet2) |
| [LiveCC](https://arxiv.org/abs/2504.16030) | Chen et al., CVPR 2025 | Real-time video commentary, trained by interleaving ASR words with frames by timestamp. | [Project](https://showlab.github.io/livecc) |
| [VideoLLM-online](https://arxiv.org/abs/2406.11816) | Chen et al., CVPR 2024 | Dialogue inside a continuous video stream, including when to respond during the stream. | [Code](https://github.com/showlab/VideoLLM-online) |

### Simplex Omni Models

The model receives the whole input and returns one answer. It does not have to decide, on its own, when to speak during a live stream.

| Model | Venue | What it does | Links |
| --- | --- | --- | --- |
| [Qwen2.5-Omni](https://arxiv.org/abs/2503.20215) | Qwen Team, arXiv 2025 | Text, image, audio, and video in. Text and streaming speech out, with a Thinker–Talker design. | [Code](https://github.com/QwenLM/Qwen2.5-Omni) |
| [MiniCPM-o 2.6](https://huggingface.co/openbmb/MiniCPM-o-2_6) | OpenBMB, 2025 | Vision, speech, and multimodal live streaming in one model. Later full-duplex interaction is in MiniCPM-o 4.5. | [Code](https://github.com/OpenBMB/MiniCPM-o) |
| [Qwen3-Omni](https://arxiv.org/abs/2509.17765) | Qwen Team, arXiv 2025 | Next model in the same series. MoE Thinker–Talker, longer audio, and lower streaming latency. | [Code](https://github.com/QwenLM/Qwen3-Omni) |
| [Qwen3.5-Omni](https://arxiv.org/abs/2604.15804) | Qwen Team, arXiv 2026 | Later model in the same series. Adds native turn-taking and interruption, plus longer audio and video context. | [API](https://www.alibabacloud.com/help/en/model-studio/qwen-omni) |
| [MiMo-V2-Omni](https://mimo.xiaomi.com/mimo-v2-omni) | Xiaomi, 2026 | Omni-modal model for text, image, video, and audio, with agentic use. No technical report found. | [Page](https://mimo.xiaomi.com/mimo-v2-omni) |
| [VideoChat](https://arxiv.org/abs/2305.06355) | Li et al., arXiv 2023 | Chat-centric video understanding. A learnable interface connects video models to a language model. | [Code](https://github.com/OpenGVLab/Ask-Anything) |
| [OmniVinci](https://arxiv.org/abs/2510.15870) | Ye et al., ICLR 2026 | Open omni-modal understanding of image, video, audio, and text, with explicit vision–audio alignment. | [Project](https://nvlabs.github.io/OmniVinci/) |

### Duplex Audio Models

Spoken models that can listen and speak at the same time.

| Model | Venue | What it does | Links |
| --- | --- | --- | --- |
| [Moshi](https://arxiv.org/abs/2410.00037) | Défossez et al., arXiv 2024 | Full-duplex speech-to-speech dialogue. The model and the user are two parallel audio streams, so overlap and interruption are part of the model. | [Code](https://github.com/kyutai-labs/moshi) |
| [Sesame CSM](https://github.com/SesameAILabs/csm) | Sesame, 2025 | Conversational speech generation from text and prior audio. The open weights generate speech. They do not themselves run a speech-to-speech duplex dialogue. | [Code](https://github.com/SesameAILabs/csm) |
| [Realtime-Venus-Audio](https://arxiv.org/abs/2609.13814) | Venus Team, arXiv 2026 | Spoken full-duplex model in the Realtime-Venus system. It handles interruption, backchannels, other-directed speech, and background speech. | |

## Omni Evaluation

Benchmarks for whether a model has the capability, rather than whether a demo sounds fluent.

### Simplex Omni Evaluation

The model receives the input, including a stream up to the query time, and returns one answer. This does not require simultaneous speaking and listening.

| Paper | Venue | What it evaluates | Links |
| --- | --- | --- | --- |
| [StreamingBench](https://arxiv.org/abs/2411.03628) | Lin et al., arXiv 2024 | Streaming video QA: real-time visual, omni-source, and contextual understanding. | [Code](https://github.com/THUNLP-MT/StreamingBench) |
| [Video-MME](https://arxiv.org/abs/2405.21075) | Fu et al., CVPR 2025 | Video QA across short, medium, and long videos, with subtitles and audio. | [Project](https://video-mme.github.io/home_page.html) |
| [OVO-Bench](https://arxiv.org/abs/2501.05510) | Li et al., CVPR 2025 | Timestamped online video QA: backward tracing, real-time perception, and forward responding. | [Code](https://github.com/JoeLeelyf/OVO-Bench) |
| [AV-Odyssey Bench](https://arxiv.org/abs/2412.02611) | Gong et al., arXiv 2024 | Audio-visual questions that require both modalities. | [Code](https://github.com/AV-Odyssey/AV-Odyssey) |
| [OmniBench](https://arxiv.org/abs/2409.15272) | Li et al., NeurIPS 2025 | Joint reasoning over image, audio, and text. | [Project](https://m-a-p.ai/OmniBench/) |
| [UNO-Bench](https://arxiv.org/abs/2510.18915) | Chen et al., arXiv 2025 | Uni-modal and omni-modal tasks under one ability taxonomy. | [Code](https://github.com/meituan-longcat/UNO-Bench) |
| [Daily-Omni](https://arxiv.org/abs/2505.17862) | Zhou et al., arXiv 2025 | Audio-visual QA that requires cross-modal temporal alignment. | [Code](https://github.com/Lliar-liar/Daily-Omni) |
| [WorldSense](https://arxiv.org/abs/2502.04326) | Hong et al., arXiv 2025 | Real-world video QA in which both audio and vision are required. | [Project](https://jaaackhongggg.github.io/WorldSense/) |
| [AVUT](https://arxiv.org/abs/2503.19951) | Yang et al., EMNLP 2025 | Audio-centric video understanding. Questions are filtered so text alone is not enough. | [Code](https://github.com/lark-png/AVUT) |
| [Video-Holmes](https://arxiv.org/abs/2505.21374) | Cheng et al., arXiv 2025 | Complex video reasoning that connects clues scattered across a clip. | [Code](https://github.com/TencentARC/Video-Holmes) |
| [OmniMMI](https://arxiv.org/abs/2503.22952) | Wang et al., CVPR 2025 | Streaming understanding and proactive reasoning. The same paper releases M4-IT. | [Project](https://omnimmi.github.io/) · [M4-IT](https://huggingface.co/datasets/ColorfulAI/M4-IT) |
| [ViSpeak](https://arxiv.org/abs/2503.12769) | Fu et al., ICCV 2025 | Responding to instructions carried in the visual stream. Includes ViSpeak-Bench. | [Code](https://github.com/HumanMLLM/ViSpeak) · [Bench](https://github.com/HumanMLLM/ViSpeak-Bench) |

### Duplex Omni Evaluation

The model keeps listening while it can speak, and decides both when to respond and what to say.

| Paper | Venue | What it evaluates | Links |
| --- | --- | --- | --- |
| [Omni-DuplexEval](https://arxiv.org/abs/2605.17360) | He et al., arXiv 2026 | Full-duplex interaction: continuous description and proactive reminders, scored on content and timing. | [Code](https://github.com/OpenBMB/Omni-DuplexEval) |
| [OmniPro](https://arxiv.org/abs/2605.18577) | Zhao et al., arXiv 2026 | Proactive response on audio-visual streams. Online mode lets the model choose when to speak. | [Project](https://ruixiangzhao.github.io/OmniPro) · [Data](https://huggingface.co/datasets/omniproact-bench/OmniPro) |
| [OmniInteract](https://arxiv.org/abs/2605.26485) | Lu et al., arXiv 2026 | Native online audio-visual interaction, including interruption and nested turns, without future content. | [Code](https://github.com/Lucky-Lance/OmniInteract) |

### Audio Duplex Evaluation

Spoken full-duplex evaluation. The model can speak and listen at the same time. Scores cover turn-taking, when not to respond, and whether a spoken task is completed.

| Paper | Venue | What it evaluates | Links |
| --- | --- | --- | --- |
| [Full-Duplex-Bench v1.0](https://arxiv.org/abs/2503.04721) | Lin et al., arXiv 2025 | Pause handling, backchanneling, smooth turn-taking, and user interruption. Cases are selected and scored by rules. The model is expected to respond. | [Code](https://github.com/DanielLin94144/Full-Duplex-Bench) |
| [Full-Duplex-Bench v1.5](https://arxiv.org/abs/2507.23159) | Lin et al., arXiv 2025 | Cases where the model should not respond: background speech, talking to someone else, and user backchannels. GPT-4o labels respond and resume against a per-task expectation. | [Code](https://github.com/DanielLin94144/Full-Duplex-Bench) |
| [Full-Duplex-Bench v2](https://arxiv.org/abs/2510.07838) | Lin et al., ACL 2026 | Real-time multi-turn dialogue. A GPT-Realtime examiner follows a goal structure and speaks with the model live. | [Code](https://github.com/DanielLin94144/Full-Duplex-Bench) |
| [Full-Duplex-Bench v3](https://arxiv.org/abs/2604.04847) | Lin et al., arXiv 2026 | Voice-agent tool use through mock APIs in travel, finance, housing, and e-commerce, on real human speech with disfluencies. | [Code](https://github.com/DanielLin94144/Full-Duplex-Bench) · [Demo](https://daniellin94144.github.io/FDB-v3-demo/) |
| [DuplexSpeechBench-IFEval](https://arxiv.org/abs/2609.03423) | Mathur and Manocha, arXiv 2026 | Conditioning levels change how tightly a persona constrains behavior. Each role has a persona, and the score checks whether the model follows it. | [Project](https://dsb-ifeval.github.io) |
| [τ-Voice](https://arxiv.org/abs/2603.13686) | Ray et al., arXiv 2026 | Full-duplex voice agents on grounded tasks. Scores both task completion and the duplex interaction. | [Code](https://github.com/sierra-research/tau2-bench) |
| [Real-Time Voice AI Hears but Does Not Listen](https://arxiv.org/abs/2606.26083) | Bartelds et al., arXiv 2026 | Whether realtime voice systems act on tone, not only words: distress, fear, sarcasm, accent, and age. | [Project](https://real-time-voice.github.io/) |

## Real-world Omni Agents

Systems that keep an omni model in an ongoing interaction.

### Voice Agents

Spoken dialogue: listening, speaking, turn-taking, noise, overlap, and long conversations.

The table includes products used in daily life, and voice-agent companies that have scaled or drawn wide attention.

| Product | Field | What it does | Now |
| --- | --- | --- | --- |
| [Ello](https://www.ello.com/) | Education | Listens to a child and teaches reading and math one to one. Speech from children is a core problem. | Active. The product now covers reading and math for ages 4–9. |
| [BoldVoice](https://www.boldvoice.com/) | Language | Pronunciation coach for non-native English speakers, with feedback while the user speaks. | Series A in Jan 2026. Over 5 million downloads. |
| [Aurelian](https://www.ycombinator.com/companies/aurelian) | Public safety | Answers non-emergency calls for 911 centers. A detected emergency is transferred to a person, with the details already collected. | Live in centers, handling thousands of non-emergency calls a day. |
| [Sully](https://www.sully.ai/) | Clinics | Clinic agents for reception, notes, and coding. They read the record and write approved work back. | Active. Used to recover abandoned patient calls and clinic documentation. |
| [Sonia](https://soniahealth.com/) | Mental health | Voice or text support for mental health. It is not a licensed therapist and not for a crisis. | Active consumer app. HIPAA-compliant, with memory across conversations. |
| [Beyz](https://beyz.ai/) | Hiring | Listens during an interview or meeting and shows the candidate a live answer structure, including on phone screens. | Active since 2024. Also has mock interviews and meeting notes. |
| [Opalite Health](https://www.ycombinator.com/companies/opalite-health) | Healthcare | Real-time medical interpreter so a visit does not wait for a human interpreter. Also drafts the visit note. | In daily use across 10+ US states. |
| [Evergrove](https://www.evergrovelabs.com/) | Workers' compensation | Voice agents that coordinate care after a workers' compensation claim, so rehab is not stuck on phone, fax, and email. | On track for more than 500,000 calls a year. |
| [Elite](https://www.ycombinator.com/companies/elite) | Clinics | Answers clinic calls and finishes scheduling, triage, refills, and intake in the EHR. | Founded 2026. Team of 2. Early. |
| [Vapi](https://vapi.ai/) | Infrastructure | Developer platform for building and deploying phone agents. | Series B in May 2026, $50M. Over 1 billion calls, and over 1 million developers. |
| [Bland](https://www.bland.ai/) | Customer calls | Phone, SMS, and chat agents for complex customer conversations. | Series C in June 2026, $50M. Total funding above $100M. |
| [HappyRobot](https://www.happyrobot.ai/) | Enterprise operations | Began as a voice agent for freight brokers. Now runs operations across voice, email, documents, and the web. | Series C in Aug 2026, $150M, about a $1.2B valuation. Customers include DHL and Uber. |
| [Avoca](https://www.avoca.ai/) | Home services | Answers calls and books jobs for home-service businesses. | More than $125M raised by April 2026, at a $1B valuation. On track to book $1B in jobs this year. |
| [Phonely](https://www.phonely.ai/) | Inbound calls | Inbound agents that answer, route, and book appointments. | Series A in April 2026, $16M. |

### Audio-Visual Agents

Agents that see and hear together: meetings, embodied perception, and reference to objects or events in a live scene.

These products use video, a camera, or a shared screen in the interview or the call. The research interviewers watch, then ask the next question. Tavus talks face to face and reads the person while the call is going.

| Product | Field | What it does | Now |
| --- | --- | --- | --- |
| [Conveo](https://conveo.ai/) | User research | Video interviews. Follow-ups use speech, tone, facial expression, gestures, objects on camera, and the shared screen. | Series A, $50M. More than 400 enterprises, including Google, Unilever, and Canva. |
| [Outset](https://outset.ai/) | User research | Video interviews. Visual Intelligence reads facial expressions and what is on screen or in the scene, then probes after the answer ends. | Series B in Dec 2025, $30M. Customers include Microsoft, Uber, and Nestlé. |
| [Listen Labs](https://listenlabs.com/) | User research | Interviews that watch the shared screen and ask about what the person actually clicked or opened. Sessions also keep video and audio. | Series B in Jan 2026, $69M. About $100M raised. More than one million interviews. Customers include Microsoft, Perplexity, and Robinhood. |
| [Trooly](https://www.trooly.ai/) | User research | 45-minute interviews. The next question follows what the person said. Sessions keep full video, and the agent reads tone and expression. | Seed round in July 2026, nearly $20M. Public beta in North America. |
| [Tavus](https://www.tavus.io/) | Sales, care, learning | Face-to-face agents for sales, intake, learning, and recruiting. During the call it reads expression, gaze, and tone. | Deployed as managed agents and as an API. |
