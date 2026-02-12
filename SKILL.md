---
name: wechat-cover-prompt-generator-skill
description: 微信文章封面提示词生成。它是 baoyu-cover-image 的“提示词提取模块”，专用于剥离绘图动作，仅产出指令。
---

# WeChat Cover Prompt Generator

本技能是 `baoyu-cover-image` 体系的**轻量级前端**，旨在复用其视觉资产并产出纯中文绘图指令。

## 核心复用逻辑
1. **指令模版**：**必须**阅读并遵循 `.gemini/skills/baoyu-cover-image/references/base-prompt.md` 中的 Prompt 构建规范。
2. **视觉参数**：参考其 `references/` 下的 `types.md`、`palettes/` 和 `renderings/`。

## 任务目标
接收文本，按照 `baoyu-cover-image` 的 5 维度标准（Type, Palette, Rendering, Text, Mood）进行分析，并输出一份**纯中文**的、高质量的提示词。

## 交互流程
1. **[加载]** 读取 `baoyu-cover-image` 的全套视觉标准和 `base-prompt.md`。
2. **[推荐]** 向用户展示选定的维度组合。
3. **[产出]** 生成提示词，结束本技能任务（不触发任何绘图动作）。
