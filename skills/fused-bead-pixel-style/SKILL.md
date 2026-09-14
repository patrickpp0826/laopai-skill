---
name: fused-bead-pixel-style
description: "Generate original pixel-art prompts in the 拼豆风 style: a strict low-resolution grid, limited palette, hard-edged shading, readable silhouettes, and optional bead-like spacing. Use when the user says ‘拼豆风’, ‘拼豆像素’, ‘8-bit 像素图’, or asks to apply this saved pixel style to a new subject. Do not use for copying existing game characters, UI, logos, or general photorealistic image prompting."
metadata:
  triggers:
    - 拼豆风
    - 拼豆像素
    - 8-bit 像素图
    - Fused-Bead Pixel
---

# 拼豆风生图配方

将低分辨率像素语言和拼豆颗粒秩序应用到新的主体。先输出英文生图提示词和中文核对稿；用户明确要求生成图片时，再调用图像生成工具。

这是原创视觉配方，不对应任何特定游戏、IP、角色或主机平台。参考图只能用于提炼网格、色板、轮廓与留白，不继承具体角色、图标、构图或字体。

## 适用场景

- 像素头像、宠物、食物、日常物件、贴纸、小场景与内容卡片。
- 用户明确要求拼豆、低分辨率网格、8-bit 或硬边像素画。
- 用户希望把一个新主题转成可读、轻松、游戏感的原创小图。

不适合长篇文字海报、复杂数据图表、高度写实的人像，或对现有游戏角色与 UI 的复刻。

## 必读参考

- 每次组装提示词前读取 [references/style-fingerprint.md](references/style-fingerprint.md)。
- 需要套用模板或排查常见偏差时读取 [references/prompt-template.md](references/prompt-template.md)。

## 输入变量

- `{subject}`：主体、必要外观与动作。
- `{scene}`：场景或背景；未指定时保持单色或极简环境。
- `{mood}`：一个明确情绪；未指定时采用轻松、清晰的基调。
- `{composition}`：景别、主体位置与留白。
- `{aspect_ratio}`：未指定时，头像和物件用 `1:1`，内容卡用 `3:4`，小场景用 `16:9`。
- `{palette_mode}`：`classic`、`pastel` 或 `noir`；默认 `classic`。
- `{bead_mode}`：`pixel` 或 `fused-bead`；默认 `pixel`。后者只增加轻微、均匀的拼豆颗粒间隔，不变成真实手工成品摄影。
- `{must_include}` 与 `{must_avoid}`：用户明确要求或排除的内容。

缺失变量可合理补全，但不得借用参考图里的角色、道具、地点、文字或构图填空。

## 工作流

1. 读取 style fingerprint，抽取固定网格、色板、硬边明暗与轮廓约束。
2. 从输入提取变量；主体不明确时只补一个简单动作或一个不抢主体的环境元素。
3. 依序写英文正向提示词：固定风格层、主体、场景与情绪、构图、色板和画幅。固定风格层必须位于前 1/3。
4. 组合负向提示词：参考文件中的专属禁用项、通用禁用项及 `{must_avoid}`，去重后输出。
5. 同步生成中文核对稿。用户要求生图时，先完成质检，再以英文正向提示词生成。

## 文字与参考图

- 默认无字；需要标题时不超过 8 个汉字，并预留后期排字区。
- 禁止复刻、描摹或暗示任何现有游戏的标题字、UI、角色、地图、道具、Logo 或界面。
- 用户提供参考图时，明确写入“style only；do not copy character, icon, composition, UI, logo, or text”。
- 图片模型不能稳定输出可读文字时，生成无字底图，并按用户可商用字体方案进行后期排字。

## 输出格式

```markdown
英文 Positive prompt：...

英文 Negative prompt：...

中文核对稿：...

画幅：...
```

## 质检清单

- [ ] 所有轮廓、五官与阴影服从同一像素尺度。
- [ ] 色板符合模式限制：普通主体 4–8 色，复杂场景最多 12 色。
- [ ] 阴影是独立硬边色块，没有模糊渐变、抗锯齿或写实光效。
- [ ] 主体在缩略图仍清晰，背景不与剪影竞争。
- [ ] 未出现现有游戏角色、UI、Logo、标题字、地图或道具。
- [ ] `fused-bead` 模式没有变成真实拼豆手工照片。
