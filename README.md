# CoMotion

> Flow-Driven Dual-Path Diffusion Models for Consistent Human Motion Transfer

## 📄 Live Demo

**👉 访问论文网站： https://yqcai101-hub.github.io/comotion/**

---

## 📝 Paper Information

### Title
**CoMotion: Flow-Driven Dual-Path Diffusion Models for Consistent Human Motion Transfer**

### Authors
- **Xiangyang Wang** (Shanghai University) - wangxiangyang@shu.edu.cn
- **Yuqing Cai** (Shanghai University) - 3235721579@shu.edu.cn
- **Rui Wang** (Shanghai University, Corresponding Author) - rwang@shu.edu.cn
- **Erkang Cheng** (Nullmax (Shanghai) Co., Ltd.) - chengerkang@nullmax.ai

### Affiliations
- **Shanghai University** - School of Communication and Information Engineering
- **Nullmax (Shanghai) Co., Ltd.** - Shanghai, China

### Abstract
Despite impressive advancements in human motion transfer based on diffusion models, existing methods still struggle to generate temporally consistent and realistic human motion, often exhibiting motion discontinuities, appearance (or identity)-motion conflicts, and visual artifacts such as phantom limbs. These issues largely stem from inaccurate 2D pose or 3D SMPL mesh estimation and the lack of explicit motion modeling to capture coherent temporal dependencies across frames. To address these challenges, we introduce CoMotion, flow-driven dual-path diffusion models designed for Consistent human Motion transfer. Specifically, it consists of three units: (1) Dual-Path Motion Coordination integrates global motion priors from an auxiliary temporal branch into the main path. The main path captures fine-grained local motion via interleaved video-flow embeddings, while the auxiliary path encodes long-range temporal dependencies through external temporal blocks, ensuring globally coherent motion. (2) Structure-Aware Flow mechanism embeds 3D structural priors into 2D optical flow, guided by surface normal and Euler continuity constraints, enabling geometrically consistent and perceptually stable motion synthesis with respect to underlying 3D geometry. (3) Dual single-layer ViT module mitigates motion-appearance discrepancies. Extensive experiments demonstrate that CoMotion significantly improves the continuity of local body motion and global human motion as well as the generation quality, achieving competitive performance on benchmark datasets.

### Method Overview

![CoMotion Framework](fig/framework.png)

Given reference image and driving video, our method extracts both the Structure-Aware Flow and the Skeleton Flow as motion. Structure-Aware Flow sequences O^RGB ∈ ℝ^H × W × 3 are interleaved with the corresponding video frames I ∈ ℝ^H × W × 3 to form pseudo-continuous sequence which denoted as X = [I_1, O^RGB_1, I_2, O^RGB_2, ..., I_n, O^RGB_n] in the main path. After encoding, dual single-layer ViT module aligns and fuses motion and appearance features. The preprocessed skeleton flow sequence (2N+n) is encoded and injected into the auxiliary path (N is the half-length of adaptive window). It integrates the global motion priors to guide local human motion generation within the model. Flow-confidence mechanism leverages optical flow intensity to derive confidence scores, enabling adaptive modulation of motion guidance across different body regions.

---

## 📝 Citation

```bibtex
@article{wang2025comotion,
  title={CoMotion: Flow-Driven Dual-Path Diffusion Models for Consistent Human Motion Transfer},
  author={Wang Xiangyang and Cai Yuqing and Wang Rui and Cheng Erkang},
  year={2025}
}
```

---

## 📧 Contact

- Corresponding Author: [Rui Wang](mailto:rwang@shu.edu.cn)
- Authors: [Xiangyang Wang](mailto:wangxiangyang@shu.edu.cn), [Yuqing Cai](mailto:3235721579@shu.edu.cn), [Erkang Cheng](mailto:chengerkang@nullmax.ai)
