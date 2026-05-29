# 🌎 LeWorldModel (LeWM): Stable End-to-End JEPA from Pixels 🚀

[![Paper](https://img.shields.io/badge/arXiv-2603.19312-B31B1B.svg)](https://arxiv.org/abs/2603.19312v1)
[![HuggingFace](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Models%20%26%20Data-orange)](https://huggingface.co/collections/quentinll/lewm)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/release/python-3100/)
[![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=flat&logo=PyTorch&logoColor=white)](https://pytorch.org/)

**LeWorldModel (LeWM)** is a breakthrough **Joint-Embedding Predictive Architecture (JEPA)** that enables stable, end-to-end training of world models directly from raw pixels. Developed by researchers including **Yann LeCun**, LeWM eliminates the need for complex multi-term losses or pretrained encoders.

<p align="center">
  <img src="assets/lewm.gif" width="90%" alt="LeWorldModel in Action">
</p>

---

## 🌟 Why LeWorldModel?

Traditional World Models and JEPAs often suffer from representation collapse or require hyperparameter-heavy training. **LeWM** changes the game:

- ✅ **Stability:** The first JEPA to train stably end-to-end from raw pixels.
- ✅ **Simplicity:** Only **two loss terms** (Prediction + Gaussian Regularization).
- ✅ **Efficiency:** ~15M parameters, trains on a **single GPU** in just a few hours.
- ✅ **Speed:** Plans up to **48x faster** than foundation-model-based world models.
- ✅ **Physical Intuition:** Latent spaces encode real physical quantities and detect "surprise" events.

---

## 🛠️ Installation & Setup

Get started with LeWM in seconds using `uv`:

```bash
# Create and activate virtual environment
uv venv --python=3.10
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install core dependencies
uv pip install stable-worldmodel[train,env]
```

---

## 📊 Datasets

Our models are benchmarked on diverse 2D and 3D control tasks (**PushT, Cube, Reacher, TwoRoom**).

1. **Download:** Get the HDF5 datasets from [Hugging Face](https://huggingface.co/collections/quentinll/lewm).
2. **Extract:**
   ```bash
   tar --zstd -xvf archive.tar.zst
   ```
3. **Configure:** Set your data home directory:
   ```bash
   export STABLEWM_HOME=/path/to/your/storage
   ```

---

## 🚀 Training your JEPA

LeWM uses [Hydra](https://hydra.cc/) for seamless configuration management. 

1. **Configure WandB:** Update `config/train/lewm.yaml` with your entity/project.
2. **Launch Training:**
   ```bash
   python train.py data=pusht
   ```

Checkpoints are automatically saved to your `$STABLEWM_HOME`.

---

## 🧠 Planning & Evaluation

Evaluate your trained world model on control tasks:

```bash
# Evaluate on PushT
python eval.py --config-name=pusht.yaml policy=pusht/lewm
```

> **Note:** `policy` should be the path relative to `$STABLEWM_HOME` without the `_object.ckpt` suffix.

---

## 📦 Pretrained Models

Skip training and dive straight into evaluation with our pretrained checkpoints:

| Task | Checkpoint | Link |
| :--- | :--- | :--- |
| 🤖 **PushT** | `lewm-pusht` | [HF Hub](https://huggingface.co/quentinll/lewm-pusht) |
| 🧊 **Cube** | `lewm-cube` | [HF Hub](https://huggingface.co/quentinll/lewm-cube) |
| 🚪 **TwoRooms** | `lewm-tworooms` | [HF Hub](https://huggingface.co/quentinll/lewm-tworooms) |
| 🎯 **Reacher** | `lewm-reacher` | [HF Hub](https://huggingface.co/quentinll/lewm-reacher) |

---

## 📝 Citation

If you use LeWorldModel in your research, please cite our work:

```bibtex
@article{maes_lelidec2026lewm,
  title={LeWorldModel: Stable End-to-End Joint-Embedding Predictive Architecture from Pixels},
  author={Maes, Lucas and Le Lidec, Quentin and Scieur, Damien and LeCun, Yann and Balestriero, Randall},
  journal={arXiv preprint},
  year={2026}
}
```

---

## 🤝 Contributing & Support

- 🐛 **Issues:** Found a bug? Open an [issue](https://github.com/lucas-maes/le-wm/issues).
- 📧 **Contact:** Reach out to `lucas.maes@mila.quebec` for collaborations.
- ⭐ **Star us:** If you like this project, give it a star on GitHub!

---

## 📈 Star History

<div align="center">
  <a href="https://www.star-history.com/?repos=ishandutta2007%2FLe-World-Model&type=date&legend=bottom-right">
   <picture>
     <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=ishandutta2007/Le-World-Model&type=date&theme=dark&legend=bottom-right" />
     <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=ishandutta2007/Le-World-Model&type=date&legend=bottom-right" />
     <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=ishandutta2007/Le-World-Model&type=date&legend=bottom-right" />
   </picture>
  </a>
</div>

---


<p align="center">
  Built with ❤️ for the World Modeling Community.
</p>

<!-- SEO Keywords: Joint-Embedding Predictive Architecture, JEPA PyTorch, World Model Robotics, Yann LeCun JEPA, LeWorldModel, Predictive Coding, Self-Supervised Learning, Latent Energy-based World Model -->
