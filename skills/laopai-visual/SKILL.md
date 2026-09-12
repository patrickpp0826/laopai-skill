---
name: laopai-visual
description: 用 Laopai 风格库生成文章封面、小红书卡片、正文配图和自拍影像。用于将用户的选题、文章或照片编译为一个已选定的可复用视觉风格；不用于纯文字写作或没有视觉产物的任务。
---

# Laopai Visual

## 核心原则

`laopai-visual` 是一个视觉工作流，不拥有某一条固定风格。每次生成必须选择且只选择一个 `styles/` 中的风格原子，再将它编译到具体输出形状。

最终提示词必须把内容、输出形状、构图和风格融合为一份完整视觉说明；不要把“风格词”作为松散后缀附加在普通提示词末尾。

## 输出形状

- `landscape-cover`：文章横版封面；默认 16:9，X 用 5:2。
- `xiaohongshu-card`：小红书封面或内容卡片；默认 3:4。
- `article-illustration`：正文场景图；默认 16:9。
- `selfie`：人物参考照片的风格化自拍；默认 4:5。

## 资源

1. 先读 [references/style-catalog.md](references/style-catalog.md)。
2. 读 [references/prompt-blueprint.md](references/prompt-blueprint.md)。
3. 画面包含可见文字或需要后期排字时，读 [references/font-licensing.md](references/font-licensing.md)。
4. 用户提供图片、作品或品牌作为设计参考时，读 [references/reference-material-policy.md](references/reference-material-policy.md)。
5. 选择一个 style 后，读：
   - `../../styles/{style-id}/META.md`
   - `../../styles/{style-id}/STYLE.md`

当前只有 `hong-kong-editorial` 时，直接使用它；未来出现多个风格后：用户已指定则严格使用，未指定时根据内容推荐三个匹配风格并等待选择，除非用户明确说由你决定。

## 工作流

1. 从输入中提取输出形状、比例、标题、可选副标题、内容摘要、视觉主体、用户约束与禁用项。长文章只保留摘要，不复制全文。
2. 读取选定 style 的 metadata 与 style atom，提炼必须保留的构图、材料、色彩、字体方向与禁用项。
3. 用 [references/prompt-blueprint.md](references/prompt-blueprint.md) 编译一份完整提示词，消除全部占位符。
4. 先保存为 `laopai-assets/{slug}/prompts/{shape}.md`，再调用可用图像生成工具生成一张图片；用户要求 prompt-only 时跳过出图。
5. 需要多尺寸时，每个比例独立编译与生成，不能通过裁切或拼图替代。

## 共同约束

- 每张图只保留一个视觉中心、一个主标题和可选的一句短副标题。
- 模型生成中文不稳定时，减少图中文字；主标题不超过 14 个汉字，副标题不超过 18 个汉字。文字更多时优先生成无字底图。
- 不默认添加账号名、logo、品牌名或虚构地点。
- 不把艺术家姓名作为模仿目标；将参考转写为可观察的视觉特征。
- 不从截图猜测字体授权；来源或许可证无法核验时，改用字体白名单中的替代项。
- 参考图只用于提炼抽象规则，不复制其中的字标、商标、插画、摄影、文案或水印。
- 图片工具只返回内联预览时，不扫描宽泛目录猜测输出文件。

## 输出

说明使用的输出形状、比例、style ID、生成结果路径和提示词路径。若用户指定了多图套装，逐项列出。
