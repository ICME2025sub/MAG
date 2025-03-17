# Make-A-Game (MAG): A Novel Paradigm for Interactive Game Rendering

[![arXiv](https://img.shields.io/badge/arXiv-Paper-red.svg?logo=arxiv)](your_arxiv_link_here)  (waiting for final decision, anonymous now)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black?logo=github)](https://github.com/ICME2025sub/MAG/)

---

## Introduction

![](
https://github.com/ICME2025sub/MAG/blob/main/material/compare.png)

The video game industry experiences exponential growth, with rising demands for personalized, immersive content; however, traditional manually coded game engines prove increasingly prohibitive in cost and time. In response, generative video models have emerged as powerful alternatives, yet existing models face significant limitations, such as weak multimodal controllability and issues of spatial misalignment and autoregressive drift.

This work introduces **Make-A-Game (MAG)**, the first interactive game simulation model leveraging the Diffusion Transformer (DiT) architecture integrated with novel control modules. MAG employs a backbone composed of stacked UC-3DMMDiT blocks to handle complex environments, coupled with lightweight Action Prompt Blocks (APBs) to facilitate precise and interactive character control.

---

## Contributions

- **Novel DiT-based Interactive Model:** Propose MAG, the first DiT-based model specifically designed for interactive game video generation, adopting a "backbone + lightweight branch" architecture to achieve superior quality and versatile control.
- **Unified Multi-Modal Control (UC-3DMMAttn):** Introduce the UC-3DMMAttn module, effectively integrating spatial and non-spatial alignment-based control signals within the DiT backbone.
- **Action Prompt Blocks (APBs):** Design APBs to deliver real-time entity manipulation, maintaining background stability and eliminating autoregressive drift.
- **Three-Stage Training Pipeline:** Develop a comprehensive three-stage training and data preparation pipeline, achieving state-of-the-art performance across multiple quantitative metrics.

---

## Methodology Overview

![](
https://github.com/ICME2025sub/MAG/blob/main/material/overview.png)

MAG's architecture consists of three core modules:

1. **Encoder Composition:** Utilizing pretrained encoders (CLIP, mT5, WFVAE) to compress multimodal inputs into latent representations.
2. **Unified Control 3D Multi-Modal Diffusion Transformer (UC-3DMMDiT Block):** Integrates spatial and non-spatial alignment-based control signals within the DiT framework, enhancing environment generation fidelity.
3. **Action Prompt Block (APB):** A lightweight, plug-and-play component enabling precise and real-time character action control, decoupling entity movements from background rendering to mitigate autoregressive drift.

The overall generation process is formally defined as:

```math
z_{gen} = f_D(f_{UC}(f_E(z_f, z_c, z_{text})) + APB(a))
```

---

## Experimental Results

### Quantitative Results

We rigorously evaluated MAG against state-of-the-art video generation models, using a comprehensive set of metrics covering both video quality and control performance. MAG consistently achieved top scores in temporal coherence, dynamic fluidity, and multi-modal control performance. 

![](https://github.com/ICME2025sub/MAG/blob/main/material/tab2.png)

### Ablation Studies

- **Environmental Control (UC-3DMMAttn):** UC-3DMMAttn significantly enhances both video quality and spatial alignment compared to simplified control approaches.

![](https://github.com/ICME2025sub/MAG/blob/main/material/tab3.png)

- **Action Control (APB):** APB dramatically improves subject and background consistency, validating its necessity for effective interactive control.

![](https://github.com/ICME2025sub/MAG/blob/main/material/tab4.png)

---

## Qualitative Results

MAG demonstrates superior qualitative performance compared to contemporary commercial systems and academic models. It successfully generates core FPS game elements (HUD, mini-map, health, ammo counters) without distortion or drift. 

![](https://github.com/ICME2025sub/MAG/blob/main/material/dingxing.png)

---

## Installation and Quick Start

### Environment Setup

```bash
git clone https://github.com/ICME2025sub/MAG.git
cd MAG
pip install -r requirements.txt # coming soon
```

### Quick Usage Example

```python
from mag import MAG

# Initialize MAG
model = MAG()

# Generate interactive game video frames
output_frames = model.generate(
    video_prompt="input_video.mp4",
    text_prompt="A stealth mission in daylight through enemy-controlled terrain.",
    action_prompt=["move left", "jump", "aim weapon"]
)

# visualize or save your generated frames
```

---

## Future Directions

We envision several promising directions for future research, including:

- Enhancing MAG's scalability and efficiency for integration into large-scale industrial game development pipelines.
- Further improving per-frame visual fidelity and aesthetic quality.
- Extending MAG's generalizability to broader interactive media applications beyond gaming, such as virtual reality and interactive simulations.

---

## Related Links

- [📖 arXiv Paper](your_arxiv_link_here)
- [💻 GitHub Repository](https://github.com/ICME2025sub/MAG)
- ...(coming soon)
---

## Citation

If you find this work useful, please cite our paper as follows:

```bibtex
@article{MAG2025,
  title={Make A Game: A Novel Paradigm for Interactive Game Rendering},
  author={Anonymous(coming soon)},
  journal={ICME 2025},
  year={2025}
}
```

---

## Contact

For questions, suggestions, or further discussions, please contact us at: `anonymous user(coming soon)`

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

© 2025 MAG Team. All rights reserved.
