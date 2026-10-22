# World Model

An internal model of how the world changes, used for prediction and planning.

Three public lines are listed here. JEPA predicts a missing part in representation space. Genie generates the next frame of a world you can act in. World Labs predicts what a scene looks like from a new point in space and time, and emits an explicit 3D world.

Papers and posts for this topic are listed on this page. They are not copied into the repository README.

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

## Genie Series

DeepMind's interactive world models. The model generates a playable environment and steps it forward from actions. Genie learns those actions from unlabeled video. Genie 2 moves the same idea to 3D. Genie 3 runs in real time from a text prompt. Project Genie, released in January 2026, is a research prototype of Genie 3.

| Model | Date | Venue | What it does | Links |
| --- | --- | --- | --- | --- |
| [Genie](https://arxiv.org/abs/2402.15391) | 2024.02 | Bruce et al., ICML 2024 | Trained on unlabeled internet videos. A latent action model lets a user step through generated 2D worlds from an image, text, photo, or sketch. | [Project](https://sites.google.com/view/genie-2024/home) |
| [Genie 2](https://deepmind.google/blog/genie-2-a-large-scale-foundation-world-model/) | 2024.12 | Parker-Holder et al., DeepMind 2024 | From one image, generates a playable 3D world. Keyboard and mouse actions step the world forward, with consistency up to about a minute. Released December 4, 2024. | |
| [Genie 3](https://deepmind.google/blog/genie-3-a-new-frontier-for-world-models/) | 2025.08 | Parker-Holder and Fruchter, DeepMind 2025 | A text prompt generates a photorealistic world that can be explored in real time, at 720p and 24 frames per second, staying consistent for a few minutes. Text can also change the world, such as the weather or a new object. Announced August 5, 2025. | |

## World Labs

Fei-Fei Li's spatial-intelligence line. The model lifts text, images, or video into a persistent 3D world that a person can enter, edit, and export.

| Model | Date | Venue | What it does | Links |
| --- | --- | --- | --- | --- |
| [Marble](https://www.worldlabs.ai/blog/marble-world-model) | 2025.11 | World Labs, 2025 | Generates a persistent 3D world from text, images, video, or a coarse layout. Worlds can be edited, expanded, and exported as Gaussian splats, meshes, or video. Generally available November 12, 2025. | |
| [Atlas](https://www.worldlabs.ai/blog/atlas) | 2026.09 | World Labs, 2026 | Pretrained from scratch on text, images, video, and 3D. Predicts a new view in space and time, reconstructs scenes as point clouds or Gaussian splats, and generates camera-controlled video up to about a minute at 1440p. Announced September 1, 2026. Later versions of Marble run on this model. | |
