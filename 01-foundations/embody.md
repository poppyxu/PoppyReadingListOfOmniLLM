# Embody

Models that connect seeing and language to physical action.

A vision-language model answers in text. A vision-language-action model outputs robot motion. A world-action model also learns how the scene changes.

Posts and papers for this topic are listed on this page. They are not copied into the repository README.

## VLM

Image and text in, text out. In this line the vision-language model is the backbone. Robot actions come from the model built on top of it.

π0 starts from PaliGemma. Later π models keep the same split and change the backbone. π0.7 uses Gemma 3 4B.

| Model | Date | Venue | What it does | Links |
| --- | --- | --- | --- | --- |
| [PaliGemma](https://arxiv.org/abs/2407.07726) | 2024.07 | Beyer et al., arXiv 2024 | A 3B vision-language model for transfer. π0 initializes its backbone from these weights. | |

## VLA

Physical Intelligence's line. These four are the generalist policies and the action tokenizer they train with.

| Model | Date | Venue | What it does | Links |
| --- | --- | --- | --- | --- |
| [π0](https://www.pi.website/blog/pi0) | 2024.10 | Black et al., arXiv 2024 | First generalist policy. A PaliGemma backbone plus a flow-matching action expert, trained across tasks and robots, outputs low-level motor commands from images and text. | [Paper](https://arxiv.org/abs/2410.24164) · [Code](https://github.com/Physical-Intelligence/openpi) |
| [FAST](https://www.pi.website/research/fast) | 2025.01 | Pertsch et al., arXiv 2025 | Action tokenizer. Discrete action tokens let π0-FAST train about five times faster than flow-matching π0 on the same dexterous tasks. | [Paper](https://arxiv.org/abs/2501.09747) · [Code](https://github.com/Physical-Intelligence/openpi) |
| [π0.5](https://www.pi.website/blog/pi05) | 2025.04 | Physical Intelligence, arXiv 2025 | Co-trains on other robots, semantic subtasks, and web data. A mobile manipulator can clean a kitchen or bedroom it has not seen. | [Paper](https://arxiv.org/abs/2504.16054) · [Code](https://github.com/Physical-Intelligence/openpi) |
| [π0.7](https://www.pi.website/blog/pi07) | 2026.04 | Physical Intelligence, arXiv 2026 | Steerable generalist. A Gemma 3 4B backbone plus a flow-matching action expert. Context can include richer language, metadata, and subgoal images. | [Paper](https://arxiv.org/abs/2604.15483) |

## LingBot

Robbyant's line. LingBot-VLA is a dual-arm policy. LingBot-VLA 2.0 extends that policy to whole-body and mobile control. LingBot-World 2.0 is the interactive world model. Its remaining variants were released in September 2026.

| Model | Date | Venue | What it does | Links |
| --- | --- | --- | --- | --- |
| [LingBot-VLA](https://arxiv.org/abs/2601.18692) | 2026.01 | Wu et al., arXiv 2026 | A Qwen2.5-VL backbone plus a flow-matching action expert, trained on about 20,000 hours from 9 dual-arm robots. The same post-training recipe is tested on 100 tasks per platform. Released January 27, 2026. | [Code](https://github.com/robbyant/lingbot-vla) · [Project](https://technology.robbyant.com/lingbot-vla/) |
| [LingBot-VLA 2.0](https://arxiv.org/abs/2607.06403) | 2026.07 | Wu et al., arXiv 2026 | About 60,000 hours of pretraining: 50,000 hours of robot trajectories across 20 configurations, plus 10,000 hours of egocentric human video. The action space adds head, waist, mobile base, and dexterous hands. Future video and depth are auxiliary prediction targets. Technical report released July 8, 2026. | [Code](https://github.com/robbyant/lingbot-vla-v2) |
| [LingBot-World 2.0](https://arxiv.org/abs/2607.07534) | 2026.07 | Gao et al., arXiv 2026 | Also called LingBot-World-Infinity. A causal world model that keeps generating past a fixed clip length. A distilled variant drives 720p video at 60 frames per second. Control covers navigation, combat, archery, and shooting, and text can change the scene. A pilot agent plans the character and a director agent adds events. The report and first 14B weights are July 9, 2026. The remaining 14B variants and the 1.3B model were released September 10, 2026. | [Code](https://github.com/robbyant/lingbot-world-v2) |

## Qwen Robot

Qwen's embodied models. Qwen-VLA is one policy for manipulation, navigation, and trajectories. Qwen-RobotManip and Qwen-RobotNav train those two problems separately, on data aligned into one action format. Weights for the two Robot models are not released.

| Model | Date | Venue | What it does | Links |
| --- | --- | --- | --- | --- |
| [Qwen-VLA](https://arxiv.org/abs/2605.30280) | 2026.05 | Qwen Team, arXiv 2026 | A Qwen3.5-4B backbone plus a DiT flow-matching action decoder. Manipulation, navigation, and trajectory prediction share one action space. A text prompt names the robot and its control convention. Submitted May 28, 2026. | [Code](https://github.com/QwenLM/Qwen-VLA) · [Blog](https://qwen.ai/blog?id=qwenvla) |
| [Qwen-RobotManip](https://arxiv.org/abs/2606.17846) | 2026.06 | Qwen Team, arXiv 2026 | A manipulation policy on Qwen3.5-4B. States and actions from different robots are mapped into one 80-dimensional vector, and end-effector motion is predicted in the camera frame. About 38,100 hours come from open robot data and human video, including human-to-robot synthesis across 15 platforms. Submitted June 16, 2026. | [Code](https://github.com/QwenLM/Qwen-RobotManip) · [Blog](https://qwen.ai/blog?id=qwen-robotmanip) |
| [Qwen-RobotNav](https://arxiv.org/abs/2606.18112) | 2026.06 | Qwen Team, arXiv 2026 | A navigation model on Qwen3-VL. Task mode and observation settings, such as token budget and per-camera weight, can change at inference time, so one backbone can follow instructions, search, track, or drive. Trained on 15.6 million samples. Submitted June 16, 2026. | [Code](https://github.com/QwenLM/Qwen-RobotNav) · [Blog](https://qwen.ai/blog?id=qwen-robotnav) |

## WAM

A world-action model learns how the visual scene changes and uses that model when it produces actions. Fast-WAM keeps the video objective in training and, at test time, predicts the action from the current observation in one pass.

| Model | Date | Venue | What it does | Links |
| --- | --- | --- | --- | --- |
| [Fast-WAM](https://arxiv.org/abs/2603.16666) | 2026.03 | Yuan et al., arXiv 2026 | Video co-training stays in the loss. At test time a video diffusion transformer encodes the observation in one pass, and an action expert outputs the action. About 190 ms latency. Competitive on LIBERO, RoboTwin, and real-robot tasks. Submitted March 17, 2026. | [Code](https://github.com/yuantianyuan01/FastWAM) · [Project](https://yuantianyuan01.github.io/FastWAM/) · [Weights](https://huggingface.co/yuanty/fastwam) |

## Cosmos Series

NVIDIA's world foundation models for physical AI. Predict generates future video. Transfer rebuilds that video from controls such as depth and edges. Reason reads a scene and plans in language. Those three stayed separate models through Cosmos 2.5. Cosmos 3 puts reasoning, generation, and robot action in one omnimodal model.

| Model | Date | Venue | What it does | Links |
| --- | --- | --- | --- | --- |
| [Cosmos](https://arxiv.org/abs/2501.03575) | 2025.01 | NVIDIA, arXiv 2025 | Platform paper for the first world foundation models. It covers a video curation pipeline, video tokenizers, and diffusion and autoregressive models that predict future frames. The pretrained models are fine-tuned into a world model for a particular robot or vehicle. Announced January 6, 2025. | [Code](https://github.com/nvidia-cosmos/cosmos-predict1) · [Project](https://research.nvidia.com/labs/dir/cosmos-predict1) |
| [Cosmos-Transfer1](https://arxiv.org/abs/2503.14492) | 2025.03 | NVIDIA, arXiv 2025 | Generates video from spatial controls such as segmentation, depth, and edges, with a different weight at each location. Used to turn simulation into photoreal video and to enrich robot and driving data. Submitted March 18, 2025. | [Code](https://github.com/nvidia-cosmos/cosmos-transfer1) |
| [Cosmos-Reason1](https://arxiv.org/abs/2503.15558) | 2025.03 | NVIDIA, arXiv 2025 | A vision-language model for physical common sense and embodied reasoning. It writes a chain of thought and can name the next action in language. Released at 7B and 56B, after supervised fine-tuning and reinforcement learning. Submitted March 18, 2025. | [Code](https://github.com/nvidia-cosmos/cosmos-reason1) · [Project](https://research.nvidia.com/labs/dir/cosmos-reason1/) |
| [Cosmos-Predict2](https://developer.nvidia.com/blog/develop-custom-physical-ai-foundation-models-with-nvidia-cosmos-predict-2/) | 2025.06 | NVIDIA, 2025 | Future-state video model at 2B and 14B. A text-to-image preview conditions the video-to-world model. Supports 480p and 704p, at 10 or 16 frames per second. Announced June 11, 2025. | [Code](https://github.com/nvidia-cosmos/cosmos-predict2) |
| [Cosmos-Predict2.5](https://arxiv.org/abs/2511.00062) | 2025.10 | NVIDIA, arXiv 2025 | One flow-matching model for text-to-world, image-to-world, and video-to-world, using Cosmos-Reason1 as the text encoder. Trained on 200 million clips, then refined with reinforcement learning. Released at 2B and 14B. The same paper adds Cosmos-Transfer2.5 for sim-to-real and real-to-real transfer. Submitted October 28, 2025. | [Code](https://github.com/nvidia-cosmos/cosmos-predict2.5) · [Transfer](https://github.com/nvidia-cosmos/cosmos-transfer2.5) · [Project](https://research.nvidia.com/labs/cosmos-lab/cosmos-predict2.5/) |
| [Cosmos-Reason2](https://huggingface.co/blog/nvidia/nvidia-cosmos-reason-2-brings-advanced-reasoning) | 2025.12 | NVIDIA, 2025 | Reasoning vision-language model post-trained from Qwen3-VL. The first release is 2B and 8B, with context up to 256K tokens, point and box localization, and trajectory output. A 32B model followed on April 29, 2026. Weights released December 19, 2025. Public announcement January 5, 2026. | [Code](https://github.com/nvidia-cosmos/cosmos-reason2) |
| [Cosmos 3](https://arxiv.org/abs/2606.02800) | 2026.06 | NVIDIA, arXiv 2026 | One omnimodal model for text, image, video, audio, and action. A reasoner and a generator share a mixture-of-transformers, so one forward pass can understand a scene, predict a future world, transfer across domains, and emit a robot action. Nano is 16B and Super is 64B. Cosmos3-Nano-Policy-DROID is an open manipulation policy trained on demonstrations. Announced June 1, 2026. | [Code](https://github.com/NVIDIA/Cosmos) · [Blog](https://huggingface.co/blog/nvidia/cosmos-3-for-physical-ai) |
