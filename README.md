# Vplugins

<p align="center">
  <img src="tauri-app/public/logo.png" width="96" alt="Vplugins logo">
</p>

<p align="center">
  <strong>把 AI 图像工作流带进 Photoshop。</strong><br>
  Run AI image workflows without leaving Photoshop.
</p>

<p align="center">
  <a href="https://ps.aigctv.net">项目官网 / Website</a> ·
  <a href="https://github.com/AIGCTV/comfyui-ps-bridge-nodes/">ComfyUI 自定义节点 / Custom Nodes</a> ·
  <a href="docs/Vplugins新手快速上手.md">新手指南</a> ·
  <a href="#english">English</a>
</p>

---

## 中文

Vplugins 是面向 Adobe Photoshop 的 AI 图像工作流工具。它在 Photoshop 旁提供一条轻量 Prompt Bar，可读取当前画布、选区和参考图，调用本地 ComfyUI、RunningHub 或 Vplugins 官方功能，并将结果放回原文档。

### 为什么选择 Vplugins

- **不中断创作**：选择区域、输入提示词、生成并回传，全程留在 Photoshop。
- **本地与云端统一入口**：同时支持本地 ComfyUI、RunningHub 和官方预设功能。
- **工作流即功能**：将已调好的工作流录入为可重复使用的 Photoshop 功能，无需每次操作节点界面。
- **轻量但实用**：支持最多 5 张参考图、选区裁剪、强度、`1K / 2K / 4K`、批量生成和结果多选回传。
- **准确回到原位**：任务保留目标文档与选区定位信息，生成结果可放回对应 Photoshop 文档和区域。
- **职责清晰**：React 负责交互，Rust 负责任务与图像处理，UXP Bridge 只负责 Photoshop 操作，便于扩展不同 provider。

### 操作界面

```text
┌──────────────────────────────────────────────────────────────┐
│  + 功能   输入提示词…   参考图   裁剪   强度   2K × 1   ▶ / ■ │
└──────────────────────────────────────────────────────────────┘
```

| 区域 | 功能 |
| --- | --- |
| `+ 功能` | 选择已启用的本地、RunningHub 或官方功能 |
| 提示词 | 输入生成或编辑要求，也可显示当前功能上下文 |
| 参考图 | 添加、排序或删除参考图，最多 5 张 |
| 运行选项 | 设置裁剪、强度、分辨率和生成数量 |
| `▶ / ■` | 开始或取消当前任务 |
| 结果预览 | 查看结果，多选后放回 Photoshop |
| 设置 | 配置 provider、录入工作流、管理功能显示与顺序 |

### 快速使用

1. 从 [Vplugins 官网](https://ps.aigctv.net) 获取并安装 Vplugins，然后启动 Photoshop。
2. 打开 Vplugins Prompt Bar，确认界面显示 Photoshop 已连接。
3. 点击左侧 `+` 选择功能，输入提示词，并按需添加参考图或 Photoshop 选区。
4. 设置分辨率、数量、强度等选项，点击 `▶` 运行。
5. 在结果预览中选择图片，将其放回当前 Photoshop 文档。

详细步骤见 [新手快速上手](docs/Vplugins新手快速上手.md) 和 [完整使用说明](docs/使用介绍.md)。

### 使用本地 ComfyUI

1. 安装 [comfyui-ps-bridge-nodes](https://github.com/AIGCTV/comfyui-ps-bridge-nodes/) 自定义节点。
2. 在 Vplugins 设置页填写 ComfyUI 地址（默认 `http://127.0.0.1:8188`）和本地目录。
3. 在 ComfyUI 中用 VP 节点制作并导出 API Workflow。
4. 在 Vplugins 的“功能录入”中扫描工作流，再到“功能展示”中启用和排序。
5. 回到 Prompt Bar，像普通 Photoshop 功能一样运行该工作流。

> 本地自定义功能使用你的本机 ComfyUI，不依赖 Vplugins 会员。模型、插件和显存需求由具体工作流决定。

### 支持Photoshop版本

支持Adobe Photoshop 24.0 或更高版本、兼容windows及Mac。

---

<a id="english"></a>

## English

Vplugins brings AI image workflows into Adobe Photoshop. Its lightweight Prompt Bar can read the current canvas, selection, and reference images, run a local ComfyUI workflow, RunningHub workflow, or an official Vplugins feature, and return the result to the original document.

### Why Vplugins

- **Stay in Photoshop**: select, prompt, generate, and place results without breaking your creative flow.
- **One entry point for local and cloud workflows**: use local ComfyUI, RunningHub, and official presets from the same interface.
- **Turn workflows into reusable tools**: register a tuned workflow once and run it like a regular Photoshop feature.
- **Compact but capable**: up to 5 reference images, selection-based cropping, strength control, `1K / 2K / 4K`, batch generation, and multi-select result placement.
- **Place results where they belong**: document and selection bounds travel with the task so results can return to the correct Photoshop document and region.
- **Clean architecture**: React handles interaction, Rust handles tasks and image processing, and the thin UXP Bridge performs Photoshop operations.

### Interface

```text
┌──────────────────────────────────────────────────────────────────────────┐
│  + Tools   Enter a prompt…   References   Crop   Strength   2K × 1   ▶ / ■ │
└──────────────────────────────────────────────────────────────────────────┘
```

| Area | What it does |
| --- | --- |
| `+ Tools` | Choose an enabled local, RunningHub, or official feature |
| Prompt | Describe the generation or edit |
| References | Add, reorder, or remove up to 5 reference images |
| Run options | Set crop mode, strength, resolution, and output count |
| `▶ / ■` | Start or cancel the current task |
| Results | Preview, select, and place images back into Photoshop |
| Settings | Configure providers, import workflows, and organize features |

### Quick start

1. Get Vplugins from the [official website](https://ps.aigctv.net), install it, and start Photoshop.
2. Open the Vplugins Prompt Bar and make sure Photoshop is connected.
3. Click `+`, choose a feature, enter a prompt, and optionally add references or a Photoshop selection.
4. Choose the resolution, output count, strength, and other options, then click `▶`.
5. Select the generated results and place them back into the current Photoshop document.

The detailed documentation is currently available in Chinese: [Quick Start](docs/Vplugins新手快速上手.md) and [User Guide](docs/使用介绍.md).

### Local ComfyUI setup

1. Install the [comfyui-ps-bridge-nodes](https://github.com/AIGCTV/comfyui-ps-bridge-nodes/) custom nodes.
2. In Vplugins Settings, enter the ComfyUI URL (default: `http://127.0.0.1:8188`) and local directory.
3. Build the workflow with VP nodes in ComfyUI and export it in API format.
4. Scan it under **Feature Import**, then enable and reorder it under **Feature Display**.
5. Return to the Prompt Bar and run the workflow like any other Photoshop feature.

> Local custom features run on your own ComfyUI installation and do not require a Vplugins membership. Model, extension, and VRAM requirements depend on the workflow.

### Supported Photoshop Versions

Supports Adobe Photoshop 24.0 or later; compatible with Windows and Mac.

---

**Website:** [https://ps.aigctv.net](https://ps.aigctv.net)<br>
**ComfyUI custom nodes:** [github.com/AIGCTV/comfyui-ps-bridge-nodes](https://github.com/AIGCTV/comfyui-ps-bridge-nodes/)
