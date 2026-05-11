# Kingdee-Design

> 金蝶设计 —— 基于 Kingdee-Design 原创框架、注入金蝶品牌色体系的 HTML 高保真原型、交互 Demo、幻灯片、设计变体探索一体化设计能力

## 简介

Kingdee-Design 是一个面向 AI Agent 的设计 Skill，让 Agent 能够产出高保真 HTML 设计作品——交互原型、幻灯片、App mockup、设计变体——而非仅仅是代码。

**核心理念**：HTML 是工具不是媒介。做原型时化身 UX 设计师，做幻灯片时化身幻灯片设计师，做 App mockup 时化身原型师。

**品牌色系（默认锁定）**：
- 主色：`#2970ff`（科技蓝）
- 渐变：`135° #2970ff → #2cbdff`
- 辅色：深海蓝 `#0d172e` / 天蓝 `#00a3f4` / 青蓝 `#2cbdff` / 冰蓝 `#eef5ff` / 紫罗兰 `#7858f9` / 琥珀 `#ffb200`

## 适用场景

| 场景 | 说明 |
|------|------|
| **交互原型** | 高保真产品 mockup，用户可点击、切换、感受流程 |
| **设计变体探索** | 并排对比多个设计方向，或用 Tweaks 实时调参 |
| **演示幻灯片** | 1920×1080 HTML deck，可当 PPT 用 |
| **App mockup** | iOS/Android 原型，带真实设备边框和状态栏 |
| **设计评审** | 5 维度专家评审（哲学一致性/视觉层级/细节执行/功能性/创新性） |

**不适用**：生产级 Web App、SEO 网站、需后端的动态系统。

## 核心能力

### 1. 核心「资产协议」

涉及具体品牌时的硬性流程，确保产出有品牌识别度：

| 资产类型 | 识别度贡献 | 必需性 |
|----------|-----------|--------|
| Logo | 最高 · 任何品牌出现 logo 就一眼识别 | **必需** |
| 产品图/渲染图 | 极高 · 实体产品的"主角" | **实体产品必需** |
| UI 截图 | 极高 · 数字产品的"主角" | **数字产品必需** |
| 色值 | 中 · 辅助识别 | 辅助 |

**反例警示**：只用 CSS 剪影/SVG 手画代替真实产品图 → 产出是「通用科技动画」，品牌识别度归零。

### 2. Junior Designer 工作流

不闷头做大招，而是：
1. 先写 assumptions + reasoning + placeholders
2. 尽早 show 给用户
3. 用户确认后再填组件
4. 中途再 show，迭代细节

**理解错了早改比晚改便宜 100 倍**。

### 3. Variations 不给「最终答案」

给 3+ 个变体，从 by-the-book 到 novel 逐级递进，让用户 mix and match。

### 4. 反 AI Slop 清单

| 避免 | 原因 | 何时可用 |
|------|------|---------|
| 激进紫色渐变 | AI 训练语料里"科技感"的万能公式 | 品牌本身用紫渐变 |
| Emoji 作图标 | 训练语料里每个 bullet 都配 emoji | 品牌本身用 |
| 圆角卡片 + 左 border accent | 2020-2024 Material/Tailwind 烂大街组合 | 用户明确要求 |
| SVG 画人物/场景 | AI 画的永远比例诡异 | **几乎不可用** |
| CSS 剪影代替产品图 | 产出是「通用科技动画」 | **几乎不可用** |
| Inter/Roboto 作 display | 太常见，看不出是「有设计的产品」 | 品牌 spec 明确用 |

### 5. 设计方向顾问模式

需求模糊时的 Fallback 流程：

1. **深度理解需求**：提问目标受众/核心信息/情感基调
2. **顾问式重述**：用自己的话重述本质需求
3. **推荐 3 套设计哲学**：含设计师名 + 视觉特征 + 气质关键词
4. **展示预制 Showcase**：24 个样例（8 场景 × 3 风格）
5. **生成 3 个视觉 Demo**：用用户真实内容，并行生成
6. **用户选择**：选一个深化 / 混合 / 微调

### 6. App 原型专属守则

- **真图优先**：默认取 Wikimedia/Unsplash 真图，不画烂 SVG
- **设备框绑定**：必须用 `assets/ios_frame.jsx`，禁止手写 Dynamic Island
- **交付形态**：先问用户要「Overview 平铺」还是「Flow demo 单机」
- **点击测试**：交付前用 Playwright  3 项最小点击测试

## 文件结构

```
kingdee-design/
├── SKILL.md              # Skill 主文档（Agent 直接读取）
├── assets/
│   ├── deck_index.html   # 幻灯片聚合器（iframe 拼接 + 键盘导航）
│   ├── deck_stage.js     # 单文件幻灯片 web component
│   ├── ios_frame.jsx     # iPhone 15 Pro 设备框（精确规格）
│   ├── android_frame.jsx # Android 设备框
│   ├── design_canvas.jsx # 并排展示 variations
│   ├── animations.jsx    # 动画组件库
│   ├── sfx/              # 音效库（50+ 音效，分类组织）
│   └── showcases/        # 24 个预制设计样例
│       ├── cover/        # 公众号封面 × 3 风格
│       ├── ppt/          # PPT 数据页 × 3 风格
│       ├── infographic/  # 竖版信息图 × 3 风格
│       └── website-*/    # 各类网站 × 3 风格
├── references/
│   ├── workflow.md       # 问问题的模板
│   ├── design-styles.md  # 20 种设计哲学详细库
│   ├── slide-decks.md    # 幻灯片制作指南
│   ├── editable-pptx.md  # HTML→可编辑 PPTX 导出
│   ├── react-setup.md    # React+Babel 项目 setup
│   ├── critique-guide.md # 设计评审指南
│   └── ...               # 其他 18 个参考文档
└── scripts/
    ├── export_deck_pdf.mjs    # HTML→PDF 导出
    ├── export_deck_pptx.mjs   # HTML→可编辑 PPTX
    ├── html2pptx.js           # DOM→PPTX 翻译器
    └── verify.py              # Playwright 验证脚本
```

## 快速开始

### 安装到 Claude Code

```bash
# 方式 1：直接复制到 skills 目录
cp -r kingdee-design ~/.claude/skills/

# 方式 2：作为 symlink（开发时推荐）
ln -s ~/kingdee-design ~/.claude/skills/kingdee-design
```

### 基本用法

在 Claude Code 中输入触发词：

- 原型：「做原型」「设计 Demo」「交互原型」「HTML 演示」
- 幻灯片：「做幻灯片」「做个 deck」「HTML PPT」
- App：「iOS 原型」「移动应用 mockup」「app mockup」
- 设计方向：「推荐风格」「设计哲学」「配色方案」「视觉风格」
- 评审：「评审」「好不好看」「review this design」

### 示例任务

```
给平台做一个产品 Landing Page 原型
做个发布会幻灯片（5 页）
给记账 App 做 iOS 原型，展示核心功能流程
推荐几个设计风格方向，做一个 SaaS 产品落地页
```

## 设计样例画廊

Skill 内置 24 个预制样例（8 场景 × 3 风格）：

| 风格代号 | 视觉气质 |
|----------|---------|
| **风格 A** | 信息建筑派 · 黑白克制、瑞士网格、强字体层级 |
| **风格 B** | 极简主义派 · 奢侈品级留白(70%+)、微妙字重 |
| **风格 C** | 东方哲学派 · 柔和科技感、自然色、图表如艺术 |

场景覆盖：公众号封面 / PPT 数据页 / 竖版信息图 / 个人主页 / AI 导航站 / AI 写作工具 / SaaS 落地页 / 开发者文档

详见 `assets/showcases/INDEX.md`。

## 导出能力

| 格式 | 脚本 | 说明 |
|------|------|------|
| PDF | `scripts/export_deck_pdf.mjs` | 矢量文字可搜，多页合并 |
| 可编辑 PPTX | `scripts/export_deck_pptx.mjs` | 文字在 PPT 里可双击编辑 |
| PDF（单文件） | `scripts/export_deck_stage_pdf.mjs` | deck-stage 架构专用 |

**PPTX 约束**：HTML 必须符合 4 条硬约束（详见 `references/editable-pptx.md`）。

## 依赖

- Playwright（验证 + 截图 + 导出）
- pdf-lib（PDF 合并）
- pptxgenjs + sharp（PPTX 导出）
- React + Babel（inline 组件）

## 来源说明

Kingdee-Design 基于花叔的 [Huashu-Design](https://github.com/huashu-design) 原创框架，注入金蝶品牌色体系适配企业场景。

## License

MIT

---

**价值观锚点**：致良知 · 走正道 · 行王道