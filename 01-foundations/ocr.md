# OCR

Reading printed and handwritten text in images, documents, and video.

Papers for this topic are listed on this page. They are not copied into the repository README.

## OCR Model

Models that read text from a page or an image.

| Model | Venue | What it does | Links |
| --- | --- | --- | --- |
| [Xiaomi-OCR-0](https://arxiv.org/abs/2609.36136) | Chen et al., arXiv 2026 | 0.8B model for document parsing and OCR question answering. A page becomes structured text, and fields can be extracted. | [Code](https://github.com/SeerRay-Lab/Xiaomi-OCR-0) · [Weights](https://huggingface.co/SeerRay-Lab/Xiaomi-OCR-0) |

## OCR Evaluation

Benchmarks for document parsing and text recognition.

| Paper | Venue | What it evaluates | Links |
| --- | --- | --- | --- |
| [OmniDocBench](https://arxiv.org/abs/2412.07626) | Ouyang et al., CVPR 2025 | PDF document parsing across papers, textbooks, handwritten notes, and newspapers. Scores cover the full page and separate text, layout, tables, and formulas. | [Code](https://github.com/opendatalab/OmniDocBench) |
| [olmOCR-Bench](https://arxiv.org/abs/2502.18443) | Poznanski et al., arXiv 2025 | A page is transcribed to Markdown and checked with pass-or-fail tests: text present, headers and footers removed, reading order, table cells, and formula layout. Pages include math, old scans, tables, multi-column layouts, and tiny text. | [Code](https://github.com/allenai/olmocr) · [Data](https://huggingface.co/datasets/allenai/olmOCR-bench) |
| [Real5-OmniDocBench](https://arxiv.org/abs/2603.04205) | Cui et al., ECCV 2026 | The same OmniDocBench v1.5 pages, re-captured under scanning, warping, screen photography, illumination, and skew. Scores follow OmniDocBench, so a drop can be traced to the capture condition. | [Data](https://huggingface.co/datasets/PaddlePaddle/Real5-OmniDocBench) |
