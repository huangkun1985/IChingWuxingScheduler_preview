<p align="center">
  <a href="#english">English</a> • <a href="#simplified-chinese">简体中文</a>
</p>

---

<a name="english"></a>

# IChingWuxingScheduler: Ancient Philosophy Meets Modern Diffusion Models

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PyPI version](https://badge.fury.io/py/iching-wuxing-scheduler.svg)](https://badge.fury.io/py/iching-wuxing-scheduler)
<!-- Add other badges as needed -->

**IChingWuxingScheduler is a novel diffusion model sampler that integrates the ancient wisdom of I-Ching and Wuxing (the Five Elements: Wood, Fire, Earth, Metal, Water) with modern numerical methods, creating a self-regulating, dynamically evolving sampling system.**

---

## 🌟 Visual Showcase: Why Choose IChingWuxingScheduler?

Traditional schedulers can appear rigid in their handling of color, detail, and lighting. By simulating a dynamical system, IChingWuxingScheduler produces results that are more natural and vibrant.

**Prompt:** A photorealistic portrait of a pensive old man, dramatic lighting, deep shadows.

| Scheduler | Result |
| :---: | :---: |
| **IChingWuxingScheduler (Ours)** | ![Our Result](https://path-to-your/comparison_image_ours.png) |
| **SA-ODE Stable** | ![SA-ODE Result](https://path-to-your/comparison_image_sa_ode.png) |
| **UniPC** | ![UniPC Result](https://path-to-your/comparison_image_unipc.png) |
| **DPM++** | ![DPM++ Result](https://path-to-your/comparison_image_dpm.png) |

*(Note: Use your best comparison images here. An image slider for before/after comparison is even more effective!)*

---

## ✨ Key Features

*   **Philosophy-Driven Dynamical System**: Dynamically adapts sampling parameters in real-time based on the generative and inhibitory cycles of the Five Elements.
*   **Higher-Order Numerical Accuracy**: Employs a 4th-order Adams-Bashforth method for more precise trajectory prediction (average order 4.0 vs. 3.0).
*   **Edge-Aware Noise Suppression**: Intelligently suppresses noise in flat regions while preserving sharp details.
*   **ODE-SDE Hybrid Sampling**: A 97% deterministic path ensures stable convergence, while a 3% stochastic component prevents color clustering and adds vitality.
*   **Fully Adaptive**: All key parameters—from solver order and smoothing strength to step-size damping—are dynamically controlled by the Wuxing system.
*   **Significant Performance Improvement**: Achieves a [379% improvement in feature capability score](link-to-benchmark-section) compared to the baseline.

---

## 🚀 Quick Start

### 1. Installation

```bash
pip install iching-wuxing-scheduler
# Make sure you have diffusers and torch installed
pip install diffusers transformers torch
```

### 2. Usage

IChingWuxingScheduler is a drop-in replacement compatible with the `diffusers` ecosystem.

```python
from diffusers import StableDiffusionPipeline
import torch
from iching_wuxing_scheduler import IChingWuxingScheduler

# 1. Load your model
model_id = "runwayml/stable-diffusion-v1-5"
pipe = StableDiffusionPipeline.from_pretrained(model_id, torch_dtype=torch.float16)

# 2. Swap the scheduler
# Choose from various modes like 'wuxing', 'wuxing-strong', 'wuxing-film', etc.
pipe.scheduler = IChingWuxingScheduler.from_config(pipe.scheduler.config, mode='wuxing')
pipe.to("cuda")

# 3. Run the pipeline
prompt = "a masterpiece painting of a serene landscape with a flowing river, inspired by ancient Chinese art"
image = pipe(prompt, num_inference_steps=30).images[0]

image.save("wuxing_result.png")
```

---

## ☯️ Core Philosophy: Mapping the Five Elements to Sampling Parameters

We established a rigorous mathematical mapping between the philosophical concepts of the Five Elements and the key parameters of diffusion sampling. This is principled design, not metaphysics.

| Element | Philosophical Meaning | Corresponding Parameter | Role in Sampling |
| :---: | :--- | :--- | :--- |
| **Wood (木)** | Growth, Expansion | **Solver Order** | Governs the aggressiveness of extrapolation. Higher orders represent more expansive exploration. |
| **Fire (火)** | Transformation, Activity | **Velocity Smoothing Strength** | Transforms and refines the velocity field, leading to a smoother, more refined generation process. |
| **Earth (土)** | Stability, Grounding | **Step-Size Damping** | Provides stability during the convergence phase, preventing oscillations and ensuring a steady landing. |
| **Metal (金)** | Convergence, Refinement | **Final Stabilization Blending** | Refines the output in the final steps, ensuring precise and accurate convergence to the target. |
| **Water (水)** | Fluidity, Adaptation | **Threshold Parameters** | Adjusts the thresholds for various phase transitions, allowing the sampling process to flow and adapt flexibly. |

This system evolves through a set of coupled Ordinary Differential Equations (ODEs), solved via a 4th-order Runge-Kutta method, allowing the sampling strategy to follow the "laws of nature."

---

## 📊 Benchmarks & Analysis

Our paper provides a detailed quantitative and qualitative analysis. Here is a summary of the key findings:

**(Embed Figure 1: Wuxing System Evolution and Figure 2: 7 Key Advantages from your paper here)**

*   **Figure 1** demonstrates how the Wuxing system evolves from a balanced initial state to a saturated state, modulating scheduler parameters in real-time.
*   **Figure 2** details the overwhelming advantages of IChingWuxingScheduler across 7 key technical dimensions compared to SA-ODE Stable.

---

## ⚙️ Configuration Modes

To suit different needs, we provide several preset modes:

*   `wuxing` (default): A balanced mode suitable for most scenarios.
*   `wuxing-strong`: Enhanced element coupling for more pronounced dynamic effects.
*   `wuxing-stable`: Reduced SDE, increased damping for more stable results.
*   `wuxing-sharp`: Minimal smoothing to maximize edge preservation.
*   `wuxing-film`: Moderate SDE for generating results with a cinematic quality.
*   ... (and others)

---

## 🎓 Citation

If you use IChingWuxingScheduler in your research, please cite our paper:

```bibtex
@misc{eddy2025ichingwuxing,
      title={IChingWuxingScheduler: Ancient Philosophy Meets Modern Diffusion Sampling}, 
      author={Eddy},
      year={2025},
      eprint={your-arxiv-id},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

## 🤝 Contributing

We welcome all contributions! Please see `CONTRIBUTING.md` for more details.

## 📜 License

This project is licensed under the [MIT License](LICENSE).

<br>
<hr>
<br>

<a name="simplified-chinese"></a>

# IChingWuxingScheduler: 古老东方哲学与现代扩散模型的融合

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PyPI version](https://badge.fury.io/py/iching-wuxing-scheduler.svg)](https://badge.fury.io/py/iching-wuxing-scheduler)
<!-- 可根据需要添加其他徽章 -->

**IChingWuxingScheduler 是一个新颖的扩散模型采样器，它将《易经》和五行（木、火、土、金、水）的古老智慧与现代数值方法相融合，创建了一个能自我调节、动态演化的采样系统。**

---

## 🌟 效果展示：为什么选择 IChingWuxingScheduler？

传统的调度器在处理色彩、细节和光影时可能显得僵硬。IChingWuxingScheduler 通过模拟一个动态系统，生成了更自然、更富有生机的结果。

**提示词 (Prompt):** A photorealistic portrait of a pensive old man, dramatic lighting, deep shadows. (一位沉思老人的写实肖像，戏剧性的光照，深邃的阴影。)

| 调度器 (Scheduler) | 结果 (Result) |
| :---: | :---: |
| **IChingWuxingScheduler (我们的)** | ![我们的结果](https://path-to-your/comparison_image_ours.png) |
| **SA-ODE Stable** | ![SA-ODE的结果](https://path-to-your/comparison_image_sa_ode.png) |
| **UniPC** | ![UniPC的结果](https://path-to-your/comparison_image_unipc.png) |
| **DPM++** | ![DPM++的结果](https://path-to-your/comparison_image_dpm.png) |

*(注意：请在此处使用你最好的对比图。如果能使用图像滑块进行前后对比，效果会更棒！)*

---

## ✨ 核心特性

*   **哲学驱动的动态系统**：基于五行生克理论，实时自适应地调整采样参数。
*   **高阶数值精度**：采用四阶 Adams-Bashforth 方法，实现更精确的轨迹预测 (平均阶数 4.0 vs 3.0)。
*   **边缘感知噪声抑制**：在保留清晰细节的同时，智能地在平滑区域抑制噪声。
*   **ODE-SDE 混合采样**：97% 的确定性路径确保稳定收敛，3% 的随机性注入避免色彩聚类，为画面增添活力。
*   **完全自适应**：从求解器阶数、平滑强度到步长阻尼，所有关键参数均由五行系统动态控制。
*   **显著的性能提升**：与基线相比，[特性能力得分提升了 379%](link-to-benchmark-section)。

---

## 🚀 快速开始

### 1. 安装

```bash
pip install iching-wuxing-scheduler
# 请确保已安装 diffusers 和 torch
pip install diffusers transformers torch
```

### 2. 使用方法

IChingWuxingScheduler 可作为直接替代品，与 `diffusers` 生态系统完美兼容。

```python
from diffusers import StableDiffusionPipeline
import torch
from iching_wuxing_scheduler import IChingWuxingScheduler

# 1. 加载你的模型
model_id = "runwayml/stable-diffusion-v1-5"
pipe = StableDiffusionPipeline.from_pretrained(model_id, torch_dtype=torch.float16)

# 2. 替换调度器
# 你可以从 'wuxing', 'wuxing-strong', 'wuxing-film' 等多种模式中选择
pipe.scheduler = IChingWuxingScheduler.from_config(pipe.scheduler.config, mode='wuxing')
pipe.to("cuda")

# 3. 运行 pipeline
prompt = "a masterpiece painting of a serene landscape with a flowing river, inspired by ancient Chinese art"
image = pipe(prompt, num_inference_steps=30).images[0]

image.save("wuxing_result.png")
```

---

## ☯️ 核心理念：五行与采样参数的映射

我们将五行元素的哲学内涵与扩散采样的关键参数进行了严谨的数学映射。这是有原则的设计，而非玄学。

| 五行元素 | 哲学内涵 | 对应采样参数 | 在采样中的作用 |
| :---: | :--- | :--- | :--- |
| **木 (Wood)** | 生长、扩张 | **求解器阶数 (Solver Order)** | 控制外插的积极性。高阶代表更具扩张性的探索。 |
| **火 (Fire)** | 转化、活力 | **速度平滑强度 (Velocity Smoothing)** | 转化和精炼速度场，使生成过程更平滑、更精致。 |
| **土 (Earth)** | 稳定、承载 | **步长阻尼 (Step-Size Damping)** | 在收敛阶段提供稳定性，防止振荡，确保平稳“着陆”。 |
| **金 (Metal)** | 收敛、精炼 | **最终稳定性混合 (Final Stabilization)** | 在最后阶段精炼输出，确保结果精确收敛。 |
| **水 (Water)** | 流动、适应 | **阈值参数 (Thresholds)** | 调节各个阶段转换的阈值，使采样过程能够灵活流动和适应。 |

该系统通过一组耦合的常微分方程（ODEs）进行演化，并使用四阶龙格-库塔法求解，从而使采样策略遵循“道法自然”的规律。

---

## 📊 性能基准与分析

我们的论文提供了详细的量化和质化分析。以下是关键结果的摘要：

**(在此处嵌入论文中的图1：五行系统演化 和 图2：7个关键优势)**

*   **图1** 展示了五行系统如何从一个平衡的初始状态演化至饱和状态，并在此过程中实时调节调度器的各项参数。
*   **图2** 详细对比了 IChingWuxingScheduler 在 7 个关键技术维度上相较于 SA-ODE Stable 的压倒性优势。

---

## ⚙️ 配置模式 (Modes)

为了满足不同需求，我们提供了多种预设模式：

*   `wuxing` (默认): 平衡模式，适用于大多数场景。
*   `wuxing-strong`: 增强的五行耦合，动态效果更明显。
*   `wuxing-stable`: 减少 SDE 影响，增加阻尼，使结果更稳定。
*   `wuxing-sharp`: 最小化平滑处理，以最大化保留边缘细节。
*   `wuxing-film`: 适度的 SDE，用于生成具有电影质感的画面。
*   ... (及其他模式)

---

## 🎓 如何引用

如果在您的研究中使用了 IChingWuxingScheduler，请引用我们的论文：

```bibtex
@misc{eddy2025ichingwuxing,
      title={IChingWuxingScheduler: Ancient Philosophy Meets Modern Diffusion Sampling}, 
      author={Eddy},
      year={2025},
      eprint={your-arxiv-id},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

## 🤝 如何贡献

我们欢迎任何形式的贡献！请查阅 `CONTRIBUTING.md` 文件了解更多详情。

## 📜 许可证

本项目采用 [MIT 许可证](LICENSE)。
```
