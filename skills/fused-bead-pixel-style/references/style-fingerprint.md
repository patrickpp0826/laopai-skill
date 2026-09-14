# 拼豆风 · Style Fingerprint

## 固定风格层

在英文正向提示词开头使用以下约束，并针对主题做自然语法连接：

```text
original low-resolution pixel illustration, strict consistent square grid, crisp stair-step silhouette, limited {palette_mode} palette, discrete hard-edged shadow clusters and small highlight blocks, clean negative space, no anti-aliasing, no smooth gradients, designed as an original icon or miniature scene
```

当 `{bead_mode}` 为 `fused-bead` 时，仅追加：

```text
subtle evenly spaced fused-bead grid logic, each color cell reads as a deliberate bead-like unit, still a flat graphic illustration rather than a photographed craft object
```

## 色板模式

- `classic`：深炭黑轮廓、奶油白背景、主体使用红、黄、蓝、绿中的 2–4 色。
- `pastel`：暖白背景、柔粉、天蓝、薄荷绿、淡黄，深紫灰或深棕作最小轮廓。
- `noir`：深靛蓝或炭黑背景，主体以灰蓝、暗红、琥珀黄或青绿色形成 3–6 色对比。

不要把全部颜色都用上。普通主体总色数 4–8；复杂场景总色数不超过 12。

## 构图规则

- 单物件或头像：主体占 55%–75%，四周至少保留 12% 背景。
- 小场景：只保留一个前景主体、一个地面/桌面/窗格关系和一个远景提示。
- 用阶梯形轮廓表达圆、斜线和动作；不要用模糊马赛克替代像素设计。
- 必要时才用一格深色外描边；内部色块不逐块描边。

## 专属负向提示词

```text
photorealistic, 3D render, smooth vector curves, anti-aliased edges, gradients, blur, soft airbrush shading, glossy plastic, dense texture, random noise, game screenshot, existing game character, copyrighted mascot, game UI, logo, watermark, copied title typography
```

## 通用负向提示词

```text
unreadable text, extra limbs, duplicate subject, cropped focal subject, cluttered composition
```
