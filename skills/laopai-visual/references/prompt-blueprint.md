# Laopai Visual Prompt Blueprint

将下列变量编译成自然语言提示词，不保留花括号，也不把 style atom 生硬附在末尾。

```text
Use case: {shape}
Asset type: {usage}
Aspect ratio: {ratio}

Create one finished image about “{topic}”.

Content:
- Main title: “{title}”
- Optional subtitle: “{subtitle}”
- Audience and context: {summary}
- Visual subject: {visual_subject}

Composition:
{shape-specific composition}. Keep one visual center and a safe title zone. Do not crop essential facial features or the main action.

Selected style: {style_name} / {style_id}
Apply these visible anchors: {style_anchors}. Use this material and color logic: {color_material_texture}. Preserve: {must_preserve}.

Typography:
{typography behavior}. Render only these exact short text elements: {minimal_visible_text}. If precise text cannot be guaranteed, leave a clean area for post-production rather than inventing text.

Constraints:
{user_constraints}

Avoid:
{avoid_list}; generic template design, random signage, unreadable text, watermark, contact sheet, and unrelated decoration.

Output one independent finished image only.
```

