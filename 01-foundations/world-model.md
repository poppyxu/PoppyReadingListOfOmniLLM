# World Model

An internal model of how the world changes, used for prediction and planning.

Papers for this topic are listed on this page. They are not copied into the repository README.

## JEPA Series

Joint-embedding predictive architectures. The model predicts a missing part in representation space. The line runs from a position paper to image representations, video representations, a video world model, denser features, and a later policy built on those features.

V-JEPA Policy is follow-up work by another group. It is outside Meta's JEPA releases.

| Model | Date | Venue | What it does | Links |
| --- | --- | --- | --- | --- |
| [A Path Towards Autonomous Machine Intelligence](https://openreview.net/forum?id=BZ5a1r-kVsf) | 2022 | LeCun, OpenReview 2022 | Position paper. Proposes learning an internal model of the world so a system can predict, plan, and act, and introduces the joint-embedding predictive architecture. Background for the models below. | |
| [I-JEPA](https://arxiv.org/abs/2301.08243) | 2023.01 | Assran et al., CVPR 2023 | From the visible part of an image, predicts the latent representation of masked regions. The encoder learns semantic structure. First submitted in January 2023, then published at CVPR 2023. | [Code](https://github.com/facebookresearch/ijepa) |
| [V-JEPA](https://arxiv.org/abs/2404.08471) | 2024.02 | Bardes et al., arXiv 2024 | Predicts latent representations of masked spatiotemporal regions in video, so the encoder learns motion and how events change. Training uses feature prediction, without pixel reconstruction, text supervision, or negative samples. Meta released it on February 15, 2024. | [Code](https://github.com/facebookresearch/jepa) · [Blog](https://ai.meta.com/blog/v-jepa-yann-lecun-ai-model-video-joint-embedding-predictive-architecture/) |
| [V-JEPA 2](https://arxiv.org/abs/2506.09985) | 2025.06 | Assran et al., arXiv 2025 | Pretrained on more than one million hours of internet video and images. The model anticipates actions and answers questions about video. The same paper post-trains V-JEPA 2-AC on a small set of robot trajectories, so it predicts the result of an action and plans toward a goal. Released June 11, 2025. | [Code](https://github.com/facebookresearch/vjepa2) · [Blog](https://ai.meta.com/blog/v-jepa-2-world-model-benchmarks/) |
| [V-JEPA 2.1](https://arxiv.org/abs/2603.14482) | 2026.03 | Mur-Labadia et al., arXiv 2026 | Revises the training objective and procedure so representations stay spatially detailed and consistent over time. Improves object-interaction understanding, depth estimation, and robot tasks. Released March 15, 2026. | [Code](https://github.com/facebookresearch/vjepa2) |
| [V-JEPA Policy](https://arxiv.org/abs/2609.37250) | 2026.09 | Zhang et al., arXiv 2026 | Follow-up by another group, outside Meta's JEPA releases. A frozen V-JEPA 2.1 encoder predicts future visual states, and a learned expert generates robot actions. Released September 29, 2026. | [Code](https://github.com/breez3young/VJEPA-Policy) · [Project](https://breez3young.github.io/vjepa-policy/) |
