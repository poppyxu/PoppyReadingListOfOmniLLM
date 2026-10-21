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

## WAM

A world-action model learns how the visual scene changes and uses that model when it produces actions. Fast-WAM keeps the video objective in training and, at test time, predicts the action from the current observation in one pass.

| Model | Date | Venue | What it does | Links |
| --- | --- | --- | --- | --- |
| [Fast-WAM](https://arxiv.org/abs/2603.16666) | 2026.03 | Yuan et al., arXiv 2026 | Video co-training stays in the loss. At test time a video diffusion transformer encodes the observation in one pass, and an action expert outputs the action. About 190 ms latency. Competitive on LIBERO, RoboTwin, and real-robot tasks. Submitted March 17, 2026. | [Code](https://github.com/yuantianyuan01/FastWAM) · [Project](https://yuantianyuan01.github.io/FastWAM/) · [Weights](https://huggingface.co/yuanty/fastwam) |
