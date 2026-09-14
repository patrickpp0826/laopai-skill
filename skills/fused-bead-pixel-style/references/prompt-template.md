# 拼豆风提示词模板与纠偏

## 模板

```text
{fixed_style_layer}. Create {subject}, {action_or_pose}. {scene_and_mood}. {composition}. Use {palette_mode} with no more than {color_count} colors. {bead_mode_clause}. Aspect ratio {aspect_ratio}. {must_include}.
```

对应中文核对稿必须保持同一主体、动作、环境、色板和禁用边界。

## 纠偏

| 偏差 | 只改这一处 |
| --- | --- |
| 像模糊缩小的插画 | 强化 `strict consistent square grid`、`crisp stair-step silhouette`，并禁止 anti-aliasing 与 blur。 |
| 色彩太杂 | 把总色数降为 4–6，删除非关键环境色。 |
| 主体读不出来 | 放大主体，增加深色轮廓或减少背景元素。 |
| 太像真实拼豆成品 | 明确 `flat graphic illustration, not photographed craft object`。 |
| 太像现有游戏 | 删除所有游戏名、角色相似描述与 UI 词；以新主体、场景和配色重写内容层。 |
| 文字乱码 | 删除画内文字，保留标题安全区用于后期。 |
